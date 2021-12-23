# Vue Split Pane

Split-Pane component built with vue2.0, can be split vertically or horizontally.

## [Try the demo](http://panjiachen.github.io/split-pane/demo/index.html)

### How to use?
```bash
npm install vue-splitpane

#import
import splitPane from 'vue-splitpane'

# use as global component
Vue.component('split-pane', splitPane);
```

### Example

```vue
   <split-pane v-on:resize="resize" :min-percent='20' :max-percent='40' :default-percent='30' split="vertical">
      <template slot="paneL">
        A
      </template>
      <template slot="paneR">
        B
      </template>
    </split-pane>
```

```vue
  //nested
   <split-pane v-on:resize="resize" :min-percent='20' :max-percent='40' :default-percent='30' split="vertical">
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
|    props    |    Description   |   type   |	default	|
| -----------------  | ---------------- | :--------: | :----------: |
| split       | the split type |String [horizontal,vertical] |must choose one type |
| min-percent         | 最小占比 |Number | 10 |
| max-percent         | 最大占比 |Number | 90 |
| default-percent | 默认占比 |Number | min-percent |
| class-name | 拖拽线类名 |String | '' |

| events | description | type     |
| ------ | ----------- | -------- |
| resize | 拖拽事件    | Function |
