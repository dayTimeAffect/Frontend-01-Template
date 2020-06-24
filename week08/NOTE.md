# 每周总结可以写在这里
+ block-level 表示可以被放入bfc  能独占一行的元素  flex、table、grid、block
+ block-container 表示可以容纳bfc  元素里面是正常流的 block、inline-block
+ block-box = block-level + block-container  能独占一行并且里面是正常流 block
+ block-box 如果 overflow 是 visible， 那么就跟父bfc合并