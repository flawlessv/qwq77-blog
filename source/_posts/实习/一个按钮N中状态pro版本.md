---
title: 一个按钮N中状态pro版本
tags:
  - 实习收获
  - CSS
  - React
categories:
  - 实习
---

### 需求

废话不多说直接上图
![Alt text](/public/img/shixi/button1.gif)
上个版本的用了固定宽度，固定了后两种状态的按钮宽度，但是 UI 姐姐说不可以！
所以我决定把之前正式工写的代码全删除，自己重写了一遍这里的逻辑
### 难点
  这个需求麻烦的点在于：按钮分为四种状态
  1:未安装
  2:未安装Hover => 改变背景色
  3:已安装
  4:已安装Hover => 改变按钮内容变为 **卸载**
  5:按钮不能固定宽度，**两侧padding必须不变！！**
  6:第4条hover的时候按钮的**宽度不能改变**（文本内容由已安装Hover=>‘卸载’）
  7:点击安装后鼠标尚未离开按钮的时候（也就是**第一次 Hover 的时候**）要**禁用 Hover**
    也就是说第一次安装后鼠标未离开按钮要显示已安装而不是卸载！

### 实现
首先看一下代码的结构，比较简单，就是通过判断不同的状态（是否已安装）来展示不同的UI
这里因为需求有点复杂所以代码写的有点冗余
```tsx
<div
  className={classNames({
    [styles.scene__btns__download]: true,
    [styles["scene__btns__download--default"]]:
      popupData.diffusionModel.isDefault,
    [styles["scene__btns__download--installed"]]: isInstallCurModel,
  })}
  style={{
    background: isInstallCurModel
      ? "rgba(43, 132, 255, 0.3)"
      : "rgba(43, 132, 255, 1)",
  }}
  onClick={() => {
    //第一次 Hover 的时候要禁用 Hover
    handleInstallModel();
    !isInstallCurModel && setIsFirstHover(true);
  }}
  onMouseLeave={() => setIsFirstHover(false)}
>
  {!isInstallCurModel ? (
    <p className={styles["zInstall"]}>
      <BaseIcon
        size={24}
        styleName={styles["notDefaultIcon"]}
        iconSvg={svgList.modelDl}
        style={{ marginRight: "4px" }}
      />
      {"安装"}&nbsp;
      {popupData.diffusionModel.installNum}
    </p>
  ) : (
    <p
      className={classNames({
        [styles["zInstalled"]]: !isFirstHover,
        [styles["firstHover"]]: isFirstHover,
      })}
    >
      <span>
        <BaseIcon
          size={24}
          styleName={styles["defaultIcon"]}
          iconSvg={svgList.modelInstalled}
          style={{ marginRight: "4px" }}
        />
        {"已安装 " + popupData.diffusionModel.installNum}
      </span>
      <span>
        <BaseIcon
          size={24}
          styleName={styles["defaultIcon"]}
          iconSvg={svgList.modelUninstall}
          style={{ marginRight: "4px" }}
        />
        卸载
      </span>
    </p>
  )}
</div>
```
### 难点击破！
首先看一下这里，这里就是实现上述需求7的方案，
设置一个`IsFirstHover`状态判断是否为刚刚安装，在`onMouseLeave`事件中改变对应的状态,
然后通过这个状态动态的添加/删除元素的类名
```tsx
  onClick={() => {
    //第一次 Hover 的时候要禁用 Hover
    handleInstallModel();
    !isInstallCurModel && setIsFirstHover(true);
  }}
  onMouseLeave={() => setIsFirstHover(false)}
```
这里有一个`firstHover`类，当第一次 `Hover` 的时候什么也不做，也就是按钮内容不会从已安装变为卸载
```less
.firstHover {
  width: 100%;
  height: 100%;
  border-radius: 51px;
  padding-left: 20px;
  padding-right: 24px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  > span:last-child {
    position: absolute;
    opacity: 0;
  }
  span {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &:hover {
  }
}
```
实现需求4和5的方案=>利用`flex`布局以及`opacity`属性
```less
  > span:last-child {
    position: absolute;
    opacity: 0;
  }
  span {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &:hover {
    > span:first-child {
      opacity: 0 !important;
    }
    > span:last-child {
      position: absolute;
      opacity: 1 !important;
    }
  }
```
```less
&__download {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  // width: 135px;
  // padding-left: 20px;
  // padding-right: 24px;
  height: 44px;
  column-gap: 4px;
  font-size: 16px;
  font-weight: 500;
  line-height: 20px;
  border-radius: 51px;
  color: rgba(255, 255, 255, 1);
  background-color: rgba(43, 132, 255, 1);
  overflow: hidden;
  //这是安装态的hover态！！
  &:hover:not(&--installed):not(&.zInstall):not(&.zInstalled):before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    border-radius: 51px;
    background-color: rgba(39, 119, 229, 1);
  }

  .defaultIcon {
    margin-right: 4px !important;
  }
}
.zInstall,
.zInstalled {
  width: 100%;
  height: 100%;
  border-radius: 51px;
  padding-left: 20px;
  padding-right: 24px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}
.zInstalled {
  > span:last-child {
    position: absolute;
    opacity: 0;
  }
  span {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &:hover {
    > span:first-child {
      opacity: 0 !important;
    }
    > span:last-child {
      position: absolute;
      opacity: 1 !important;
    }
  }
}
//如果刚安装，则不触发hover态
.firstHover {
  width: 100%;
  height: 100%;
  border-radius: 51px;
  padding-left: 20px;
  padding-right: 24px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  > span:last-child {
    position: absolute;
    opacity: 0;
  }
  span {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  &:hover {
  }
}
```
### 总结
 1.这种复杂的交互和样式一定要思路清晰！
 2.这B班上的是真有意思哦～
 3.加油赵世伟！