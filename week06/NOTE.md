# 有限状态机处理字符串

## 有限状态机

- 每一个状态都是一个机器
  - 在每一个机器里，我们可以做计算、存储、输出...
  - 所有的这些机器接受的输入是一致的
  - 状态机的每一个机器本身没有状态，如果我们用函数来表示的话，它应该是纯函数（无副作用）
- 每一个机器知道下一个状态
  - 每个机器都有确定的下一个状态（Moore）
  - 每个机器根据输入决定下一个状态（Mealy）



## parse HTML

- 我们用 FSM 来实现 HTML 的分析
- 在 HTML 标准中，已经规定了 HTML 的状态
- Toy-Browser 只挑选其中一部分状态，完成一个最简版本

### 解析标签

- 主要的标签有：开始标签，结束标签和自封闭标签
- 在这一步暂时忽略属性

### 创建元素

- 在状态机中，除了状态迁移，我们还会加入业务逻辑
- 我们在标签结束状态提交标签 token

### 处理属性

- 属性值分为单引号、双引号、无引号三种写法，因此需要较多状态处理
- 处理属性的方式跟标签类似
- 属性结束后，吧属性加到标签 Token 上

###  构建 DOM 树

- 从标签构建 DOM 树的基本技巧是使用栈
- 遇到开始标签时创建元素并入栈，遇到结束标签时出栈
- 自封闭节点可视为入栈后立刻出栈
- 任何元素的父元素是它入栈前的栈顶

## CSS

- 当我们创建一个元素后，立即计算CSS;
- 理论上，当我们分析一个元素时，所有CSS规则已经收集完毕
- 在真实浏览器中，可能遇到写在body的style标签，需要重新CSS计算的情况，这里我们忽略

- 在computeCSS函数中，我们必须知道元素的所有父元素才能判断元素与规则是否匹配
- 我们从上一步骤的stack，可以获取本元素所有的父元素
- 因为我们首先获取的是“当前元素”，所以我们获得和计算父元素匹配的顺序是从内向外

- 根据选择器的类型和元素属性，计算是否与当前元素匹配
- 生成computed属性 • 一旦选择匹配，就应用选择器到元素上
- CSS规则根据specificity和后来优先规则覆盖 • specificity是个四元组，越左边权重越高 • 一个CSS规则的specificity根据包含的简单选择器相加而成

