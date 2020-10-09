[相关文档](https://wangdoc.com/javascript/events/drag.html)

> 图片、链接默认可以拖拉，设置draggable为false防止其拖拉。元素节点设置draggable为true让其可以拖拉，内部文字或子节点就无法用鼠标选中

- `drag` 拖拉过程中，持续触发
- `dragstart` 被拖拉节点在拖拉开始时触发。指定拖拉的数据
- `dragend`  被拖拉节点在拖拉结束时触发
- `dragenter` 进入节点触发，如果当前节点没有该事件的监听函数，或者监听函数不执行任何操作，就意味着不允许在当前节点放下数据
- `dragover` 进入节点持续触发，只要没离开
- `dragleave` 拖拉操作离开当前节点范围触发
- `drop` 释放到目标节点时，在目标节点上触发。取出拖拉数据，并进行相关处理

