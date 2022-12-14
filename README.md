# Vue Split Pane

Split-Pane component built with vue2.0, can be split vertically or horizontally.

## 库源 demo [Try the demo](http://panjiachen.github.io/split-pane/demo/index.html)

> - 对 `panjiachen` 大佬的源码做了优化, 添加了 `max-percent` 选项
>
> - 对 `resize`  事件 优化, 只有拖拽发生, 才会触发

### How to use?

> 这是大佬的使用方法, 他的源码没对 `max-percent`  和 `resize`  优化, 需要注意

```bash
npm install vue-splitpane

#import
import splitPane from 'vue-splitpane'

# use as global component
Vue.component('split-pane', splitPane);
```

### Example

> 注意:
>
> `split-pane`标签外层容器, 必须有宽高

```vue
<split-pane
  v-on:resize="resize"
  :min-percent="20"
  :max-percent="40"
  :default-percent="30"
  split="vertical"
  class-name="my-line-class"
>
<template slot="paneL">
    A
  </template>
  <template slot="paneR">
    B
  </template>
</split-pane>
```

```vue

<split-pane v-on:resize="resize" :min-percent="20" :max-percent="40" :default-percent="30" split="vertical">
  <template slot="paneL">
    A
  </template>
  <template slot="paneR">
    <split-pane split="horizontal">
      <template slot="paneL">
        B
      </template>
      <template slot="paneR">
        C
      </template>
    </split-pane>
  </template>
</split-pane>
```

### Options

| props           | Description    |             type             |   default   |
| --------------- | -------------- | :--------------------------: | :---------: |
| split           | the split type | String [horizontal,vertical] |    必填     |
| min-percent     | 最小占比       |            Number            |     10      |
| max-percent     | 最大占比       |            Number            |     90      |
| default-percent | 默认占比       |            Number            | min-percent |
| class-name      | 拖拽线类名     |            String            |     ''      |

| events | description | type     |
| ------ | ----------- | -------- |
| resize | 拖拽事件    | Function |
