---
title: 数据结构笔记
tags:
  - 数据结构
---

### 数据结构按逻辑结构划分

[作者：纯情美少男](tencent://message/?uin=563724120)
::: warning 温馨提示
笔记这里有一个严重缺陷！右侧目录列表必须向下滑才能出现。目前这个 bug 解决工程量有点大,coding 最近要准备各种比赛和期末考试,后续会优化的,斯密马赛~
:::
1、线性结构

（1）、一般线性表

（2）、受限线性表 分为（1）、栈（顺序栈）（链栈）（共享栈）

​ （2）、队列（循环队列）（链式队列）（双端队列）

​ （3）、串

（3）、线性表推广 分为（1）、数组（一维数组）（多维数组）

​ （2）、广义表

2、非线性结构

（1）、集合

（2）、树形结构 分为（1）、一般树

​ （2）、二叉树

（3）、图状结构 分为（1）、有向图

​ （2）、无向图

### 线性表

按存储结构划分

1、顺序表

2、链表

值得注意的点：1、理解什么时候要传入参数的引用“&”

2、代码的可读性

### 顺序表

优点：可随机存取，存储密度高

缺点：要求大片连续空间，改变容量不方便

静态顺序表：数组、大小固定、内存溢出

动态顺序表

线性表的顺序表示|存储

逻辑和物理都有序

### 顺序表结构体代码

​ typedef struct{

​ ElemType \*elem;

​ int length;

​ }sqlist;

### 链表

优点：不要求大片连续空间，改变容量方便

缺点：不可随机存取，要耗费一定空间存放指针

单链表

### 用代码定义一个单链表

typedef struct LNode{

​ ElemType data;

​ struct LNode \*next;

}LNode,\*LInkList;

两种实现：

1、不带头结点 空表判断 ： L==NULL。写代码不方便

2、带头结点 空表判断： L->next==NULL。写代码方便

需要注意的点：

1、typedef 关键字的用法

2、“LinkList”等价于“LNode”

前者强调这是链表，后者强调这是结点，合适的地方用合适的名字，代码可读性更高。

### 头插尾插（含代码）

向单链表中插入一个元素可分为：头插法和尾插法

头插法代码（输出时的数据与读入时的数据顺序是相反的）：

​

```c
LinkList	CreateList_Head(LinkList	L)
​				{LinkList 	s;

​				int	x;

​				L=(LNode*)malloc(sizeof(LNode));

​				L->next=NULL;

​				scanf("%d",&x);

​				while(x!=9999){

​				s=(LNode*)malloc(sizeof(LNode));

​				s->data=x;

​				s->next=L->next;

​				L->next=s;

​				scanf("%d",&x);

​				}

​				return L;

​				}
```

尾插法代码(保证了输入数据的顺序与链表顺序的一致性)：

​ LinkList CreateList_Tail(LinkList L)

​ {

​ int x;

​ L=(LNode\*)malloc(sizeof(LNode));

​ LNode \*s;

​ LNode \*r=L;

​ scanf("%d",&x);

​ while(x!=999){

​ s=(LNode\*)malloc(sizeof(LNode));

​ s->data=x;

​ r->next=s;

​ r=s;

​ scanf("%d",&x);

​ }

​ r->next=NULL;

​ return L;

​ }

### 双链表

一个结点两个指针，可进可退

相比于单链表，单链表：无法逆向检索，有时候不太方便

​ 双链表：可进可退，存储密度更低一些（存储密度高越好）；

双链表结点定义代码

​ typedef struct DNode{

​ ElemType data;

​ struct DNode \*prior;

​ struct DNode \*next;

​ }DNode,\*DLinkList;

### 循环链表

循环单链表：表尾结点的 next 指针指向头结点

循环双链表：表头结点的 prior 指向表尾结点；

​ 表尾结点的 next 指向头结点。

### 静态链表（用数组方式实现的链表）

0 头 2（游标充当指针）

1 e2 6

2 e1 1

3 e4 -1

4

5

6 e3 3

7

8

9

L->头->e1->e2->e3->e4->NULL(-1)

单链表：各个结点在内存中星罗棋布，散落天涯。

静态链表：分配一整片连续的内存空间，各个结点集中安置。

每个元素 4B，每个游标 4B（每个结点共 8B）

设起始地址为 addr

e1 的存放地址为 addr+8\*2；

### 受限线性表

### 栈 Stack

先进后出

只能从一头进一头出

栈顶、栈底、空栈

### 顺序栈

用静态数组实现，并需要记录栈顶指针

基本操作：增删改查（）都是 O（1）的时间复杂度

两种实现：

（1）、初始化时 top==-1

入栈 s.data[++s.top]=x;

出栈 s.data[s.top--]=x;

获取栈顶元素 x=s.data[s.top];

(2)、初始化时 top=0

入栈 s.data[s.top++]=x;

出栈 s.data[--s.top]=x;

获取栈顶元素 x=s.data[s.top-1];

### 顺序栈代码实现

​ #define Stack_Init_Size 100

​ #define StackIncrement 10

​ typedef int ElemType;

​ typedef int Status;

​ //方式一

​ typedef struct{

​ ElemType \*base;//栈底指针

​ ElemType \*top;//栈顶指针

​ int stacksize;//栈的最大容量

​ }SqStack;

​ //方式二

​ typedef struct{

​ int data[MaxSize];

​ int top;

​ }SqStack;

方式 1 代码

#include <stdio.h>
\#include <stdlib.h>

\#define Stack_Init_Size 10 // 初始化栈的最大长度
\#define StackIncrement 10 // 若栈最大空间不够时，需要增加的长度
typedef int ElemType;
typedef int Status;

typedef struct {
ElemType *base; // 栈底指针
ElemType *top; // 栈顶指针
int stack_size; // 栈的最大长度
} SqStack;

// 初始化栈
Status InitStack(SqStack _S) {
// 分配初始空间
S->base = (ElemType _) malloc(Stack_Init_Size \* sizeof(ElemType));
if (!S->base) {
exit(0);
}
S->top = S->base; /// 栈顶与栈底相同
S->stack_size = Stack_Init_Size; // 栈的最大长度等于初始长度
return 1;
}

// 判断栈是否为空，只需要判断栈顶指针与栈底指针是否相同即可
Status EmptyStack(SqStack \*S) {
return S->base == S->top;
}

// 获取栈的实际长度，栈顶减去栈底指针即为栈的长度
Status LengthStack(SqStack \*S) {
if (S->top == S->base) {
return 0;
}
return (Status) (S->top - S->base);
}

// 获取栈顶的元素，参数 e 用来存放栈顶的元素
Status GetTopStack(SqStack *S, ElemType *e) {
if (S->top == S->base) {
return 0;
}
_e = _(S->top - 1);
return 1;
}

// 进栈，参数 e 是要进栈的元素
Status PushStack(SqStack _S, ElemType e) {
// 若栈的最大长度不会够用时，重新开辟，增大长度
if (S->top - S->base >= S->stack_size) {
S->base = (ElemType _)realloc(S->base, (S->stack_size + StackIncrement) * sizeof(ElemType));
if (!S->base) {
return 0;
}
// 栈顶指针为栈底指针加上栈之前的最大长度
S->top = S->base + S->stack_size;
// 栈当前的最大长度等于栈之前的最大长度与增加的长度之和
S->stack_size += StackIncrement;
}
*S->top++ = e; // 先赋值，后栈顶指针上移
return 1;
}

// 出栈，参数 e 用来存放出栈的元素
Status PopStack(SqStack *S, ElemType *e) {
if (S->base == S->top) {
return 0;
}
_e = _--S->top; // 栈顶指针先下移，后赋值
return 1;
}

// 销毁栈，释放栈空间，栈顶栈底指针置为 NULL，长度置为 0
Status DestroyStack(SqStack \*S) {
free(S->base);
S->base = S->top = NULL;
S->stack_size = 0;
return 1;
}

// 遍历栈，依次打印每个元素
Status StackTraverse(SqStack *S) {
ElemType *p;

if (S->top == S->base) {
printf("Stack is NULL.\n");
return 0;
}
p = S->top;
// 由栈顶依次向下遍历
while (p > S->base) {
p--;
printf("%d ", \*p);
}
printf("\n");
return 1;
}

int main() {
SqStack q, \*S;
S = &q;

int i, n, e;

printf("Creat a NULL Stack :\n");
InitStack(S);

printf("input the length of the Stack :\n");
scanf("%d", &n);

for (i = 1; i <= n; i++) {
scanf("%d", &e);
PushStack(S, e);
}
printf("Is the stack NULL?\n");

if (EmptyStack(S)) {
printf("Yes!\n");
} else {
printf("No!\n");
}
printf("The length of stack is %d.\n", LengthStack(S));

printf("The stack is :\n");
StackTraverse(S);

e = GetTopStack(S, &e);
printf("The top data is %d.\n", e);

printf("input the data to the stack :\n");
scanf("%d", &e);
PushStack(S, e);
printf("The new stack is :\n");
StackTraverse(S);

printf("Delete the top data : ");
e = PopStack(S, &e);
printf("%d\n", e);

printf("The new stack is :\n");
StackTraverse(S);

printf("Destroy the stack :\n");
DestroyStack(S);
StackTraverse(S);

return 0;
}

### 共享栈（含初始代码）

两个栈共享一片内存空间，两个栈从两边往中间增长

初始化 0 号栈栈顶指针初始化时 top0=-1；1 号栈初始化时 top1=MaxSize；

栈满条件 top0+1=top1；

​ #define MaxSize 10

​ typedef struct{

​ ElemType data[MaxSize];

​ int top0;

​ int top1;

​ }ShStack;

初始化栈

​ void InitStack(ShStack &s){

​ S.top0=1;

​ S.top1=MaxSize;

​ }

### 链栈（含代码）

存储结构

​ typedef struct StackNode{

​ ElemType data;

​ struct StackNode \*next;

​ }StackNode,\*LinkStack;

​ int InitLinkStack(LinkStack \*L){

​ L=(LinkStack\*)malloc(sizeof(LinkStack));//申请内存

​ if(!L->data) return 0;//申请失败

​ L->data=0;

​ L->next=NULL;

​ reutrn 1;

​ }

​ int pushStack(LinkStack \*L,ElemType e){

​ LinkStack \*n;

​ n=(LinkStack\*)malloc(sizeof(LinkStack));

​ if(!n->data) return 0;

​ n->data=e;

​ n->next=L->next;

​ L->next=n;

​ return 1;

​ }

​ int pop(LinkStack *L,ElemType *e){

​ if(!L->next) return 0;//栈空

​ LinkStack \*d=L->next;

​ \*e=d->data;

​ L->next=d->next;

​ free(d);

​ return 1;

​ }

​ //取栈顶

​ int getTop(LinkStack *L,ElemType *e){

​ if(!L->next) reutrn 0;

​ \*e=L->next->data;

​ return 1;

​ }

### 队列

先进先出，队尾插入，队头删除

### 顺序队列（含代码）

队头指针指向队头元素，队尾指针指向队尾元素的下一个位置。

初始状态（队空状态）Q.front==Q.rear==0

队满状态：Q.rear==MaxSize(可能是假满)因此，当数组长度为 len 时，满足 front=（rear+1）%len 时，队列为满。

队列长度计算公式：QueueSize=(rear-front+len)%len.

进队操作：队不满时，先送值到队尾元素，再将队尾指针加 1.

出队操作：队不空时，先取队头元素值，再将队头指针加 1.

​ #include<stdio.h>

​ #include<stdlib.h>

​ #define MaxSize 10

​ //顺序队列存储结构

​ typedef strucr{

​ int data[MaxSize];

​ int front,rear;

​ }SqQueue;

​ //初始化
​ int InitQueue(SqQueue \*Q){
​ Q->front=0;

​ Q->rear=0;

​ return 1;

​ }

​ //求顺序表长度

​ int QueueLength(SqQueue Q){

​ return Q.rear-Q.front;

​ }

​ //入队操作

​ int EnQueue(SqQueue \*Q,int e){

​ if(Q->rear==MaxSize)

​ return 0;

​ Q->data[Q->rear]=e;

​ Q->rear++;

​ return 1;

​ }

​ //出队操作

​ int DeQueue(SqQueue* Q,int* e){

​ if(Q->rear==Q->front)

​ return 0;

​ \*e=Q->data[Q->front];

​ Q->front++;

​ return 1;

​ }

### 循环队列

为什么要使用循环数组？

想象一下，加入我使用的是通常的数组，那么在使用的过程中，我们是从后面加入数据，从前面移除数据，那么随着出队和入队的进行，数组会整体向右平移，因为数组前面的元素因为出队变成了空白，变得不可使用，造成空间的浪费。综上，我们使用循环队列，就是将队首和队尾黏在一起，类似于一个 ○

不同的队首和队尾的初始化，将导致我们判断队列是否已满以及队列是否为空的方法不同。

（1）、front 和 rear 初始化均为 0，那么，front 会永远指向队首元素，而 rear 会指向队尾元素的下一格。

（2）、front 和 rear 错开，比如 front 初始化为 0，rear 初始化为 5，这种情况下 front 会永远指向队首元素，rear 会永远指向队尾元素。

如何在代码实现过程中将正常数组变成循环数组呢？

答：取余即可。

定义结构体

​ typedef struct Queue{

​ int \*data;

​ int capacity;

​ int front;

​ int rear;

​ }Queue;

队列初始化

​ void Init(Queue \*p,int capacity){

​ p->capacity=capacity;

​ p->data=(int\*)malloc(sizeof(int)星号(capacity+1));

​ p->front=0;

​ p->rear=0;

​ }

判断队列是否已满

​ int isFull(Queue \*p){

​ if((p->rear+1)%(p->capacity+1)==p->front)

​ return 1;

​ else return 0;

​ }

判断队列是否为空

​ int isEmpty(Queue \*p){

​ return p->front==p->rear;

​ }

入队操作，x 表示插入的元素

​ int enQueue(Queue \*p,int x){

​ if(isFull(p))

​ return 0;

​ else{

​ p->data[p->rear]=x;

​ p->rear=(p->rear+1)%(p->capacity+1);

​ reutrn 1;

​ }

​ }

出队操作，同时返回出队的值给 px

​ int deQueue(Queue *p,int *px){

​ if(isEmpty(p))

​ return 0;

​ else{

​ \*px=p->data[p->front];

​ p->front=(p->front+1)%(p->capacity+1);

​ return 1;

​ }

​ }

### 链队

### 双端队列

### 栈的应用

### 括号匹配

### 表达式求值

### 递归

### 队列应用

### 树

### 树的基本术语

（1）、结点：树中的一个独立单元，包含一个数据及若干个指向其子树的分支。

（2）、结点的度：结点拥有的子树的数称为结点的度。

（3）、树的度：树的度是树内各结点度的最大值。

（4）、叶子结点：度为 0 的结点称为叶子结点或终端结点。

（5）、非终端结点：度不为 0 的结点称为非终端结点或分支结点。除根结点之外，非终端结点也称为内部结点。

（6）、双亲和孩子：结点的子树的根称为该结点的孩子，相应的，该结点称为孩子的双亲。

（7）、兄弟结点：同一个双亲的孩子之间称为兄弟结点。

（8）、祖先结点：从根到该结点所经分支上的所有结点。

（9）、子孙结点：以某结点为根的子树中的任一结点称为该结点的子孙结点。

（10）、层次：结点的层次从根开始定义，根为第一层，根的孩子为第二层，以此类推。

（11）、堂兄弟结点：双亲在同一层的结点称为堂兄弟结点。

（12）、树的深度：树中结点的最大层次称为树的深度或高度。

（13）、有序树和无序树：如果将树中结点的各子树看成从左至右是有次序的（即不能互换），则称该树为有序树，否则为无序树。

（14）、森林：是 m 棵互不相交的树的集合。对树中每个结点而言，其子树的集合即为森林。由此，也可以用森林和树相互递归的定义来描述树。

### 二叉树的定义

除根结点之外的其余结点分为两个互不相交的子集 T1 和 T2，分别称为 T 的左子树和右子树，且 T1 和 T2 本身又是二叉树。

### 二叉树的性质

性质 1:在二叉树的第 i 层上至多有 2\*i-1 个结点（i>=1）。

性质 2:深度为 k 的二叉树至多有 2\*（k-1）个结点（k>=1）。

性质 3:对任何一棵二叉树 T，如果其终端结点数为 n0，度为 2 的结点数为 n2，则 n0=n2+1

满二叉树：深度为 k 且含有 2\*（k-1）个结点的二叉树。

满二叉树的特点是：每一层上的结点数都是最大结点数，即每一层 i 的结点数都是具有最大值 2\*i-1

可以对满二叉树的结点进行连续编号，约定编号从根结点开始，自上而下，自左至右。由此可引出完全二叉树的定义。

完全二叉树：深度为 k 的，有 n 个结点的二叉树，当且仅当其每一个结点都与深度为 k 的满二叉树中编号从 1 到 n 的结点一一对应时，称之为完全二叉树。

完全二叉树的特点是：（1）、叶子结点只可能在层次最大的两层上出现。

​ （2）、对任一结点，若其右分支下的子孙的最大层次为 L，则其左分支下的子孙的最大层次必为 L，或 L+1。

性质 4:具有 n 个结点的完全二叉树的深度为 log2（n）+1。

### 二叉树的顺序存储结构

​ #define MAXSIZE 100

​ typedef TElemType SqBiTree [MAXSIZE];//二叉树的最大结点数

​ SqBiTree bt;//0 号结点存储根结点

对于完全二叉树，编号为 i 的结点元素存储在定义的一维数组下标为 i-1 的分量中。

对于一般二叉树，将结点与完全二叉树的结点相对照，存储在一维数组的相应分量中即可。

### 链式存储结构

​ typedef struct BiTree{

​ TElemType data;

​ struct BiTree \*lchild;

​ struct BiTree \*rchild;

​ }BiTreeNode,\*BiTree;
