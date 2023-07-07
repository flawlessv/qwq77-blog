---
title: 实现一个按钮N种状态
tags:
  - 实习
  - CSS
  - React
# categories:
#   - 前端
---

#### 需求

废话不多说直接上图
![Alt text](/public/img/shixi/button1.gif)
没错！一个按钮要有四种状态及其不同的 hover 态，并且在点击安装后鼠标尚未离开按钮的时候（也就是第一次 Hover 的时候）要禁用 Hover

#### 实现

```tsx
<div
  className={classNames({
    [styles.scene__btns__download]: true,
    [styles["scene__btns__download--default"]]:
      popupData.diffusionModel.isDefault,
    [styles["scene__btns__download--installed"]]:
      isInstallCurModel && !isFirstHover,
    [styles["scene__btns__download--firstHover"]]: isFirstHover,
  })}
  onClick={() => {
    handleInstallModel();
    !isInstallCurModel && setIsFirstHover(true);
  }}
  onMouseLeave={() => setIsFirstHover(false)}
>
  <BaseIcon
    size={24}
    styleName={styles["notDefaultIcon"]}
    iconSvg={isInstallCurModel ? svgList.modelInstalled : svgList.modelDl}
  />
  <BaseIcon
    size={24}
    styleName={styles["defaultIcon"]}
    iconSvg={svgList.modelUninstall}
  />
  <p className={styles["notDefaultText"]}>
    {isInstallCurModel ? "已安装" : "安装"}&nbsp;
    {popupData.diffusionModel.installNum}
  </p>
  <p className={styles["defaultText"]}>卸载</p>
  {/* <p>{popupData.diffusionModel.installNum}</p> */}
</div>
```

```less
 &__download {
      display: flex;
      align-items: center;
      justify-content: center;
      position: relative;
      width: 135px;
      padding-left: 20px;
      padding-right: 24px;
      height: 44px;
      column-gap: 4px;
      font-size: 16px;
      font-weight: 500;
      line-height: 20px;
      border-radius: 51px;
      color: rgba(255, 255, 255, 1);
      background-color: rgba(43, 132, 255, 1);

      >p:first-child {
        margin-left: 4px;
      }

      &:hover:not(&--installed):not(&--firstHover):before {
        content: '';
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        border-radius: 51px;
        background-color: rgba(39, 119, 229, 1);
      }


      .defaultIcon,
      .defaultText {
        display: none;
      }

      &--installed {
        background-color: rgba(43, 132, 255, 0.3);

        &:hover:not(.scene__btns__download--default) {
          .defaultIcon,
          .defaultText {
            display: block;
          }

          .notDefaultIcon,
          .notDefaultText {
            display: none;
          }
        }
      }
      &--firstHover{
        background-color: rgba(43, 132, 255, 0.3)!important;
        &:hover:not(.scene__btns__download--default) {
        }
```
