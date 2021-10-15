> [Vue3 组件] 用于拖拽调整位置和大小的的组件，同时支持冲突检测，元素吸附对齐，实时参考线。基于[vue3-draggable-resizable](https://www.npmjs.com/package/vue3-draggable-resizable)组件修改而来，非原创。 [ Vue3 Component ] Draggable and resizable component for vue3, and, support element adsorption alignment, real-time reference line, etc. [Special Note] This component is based on [vue3-draggable-resizable](https://www.npmjs.com/package/vue3-draggable-resizable) Modified,Not original。 [New Features] Support Rotation And zIndex

## Table of Contents

- [Features](#features)
- [Usage](#Usage)
  - [Props](#props)

### Features

- Draggable and resizable
- Define handles for resizing
- Restrict movement and size in parent node
- Customize various class names
- Provide your own markup for handles
- Adsorption alignment
- Reference line
- Support Rotation
- Support zIndex

### Usage

```bash
$ npm install vue3-draggable-resizer
```

Register the Vue3DraggableResizer

```js
// >main.js
import { createApp } from "vue";
import App from "./App.vue";
import DraggableResizer from "vue3-draggable-resizer";
//default styles
import "vue3-draggable-resizer/style.css";

// You will have a global component named "DraggableResizer"
createApp(App).use(DraggableResizer).mount("#app");
```

You can also use it separately within the component

```js
// >component.js
import { defineComponent } from "vue";
import DraggableResizer from "vue3-draggable-resizer";
//default styles
import "vue3-draggable-resizer/style.css";

export default defineComponent({
  components: { DraggableResizer },
  // ...other
});
```

Here is a complete example of using "vue-template"

```vue
<template>
  <div id="app">
    <div class="parent">
      <DraggableResizer
        :initW="110"
        :initH="120"
        :z="zIndex"
        v-model:x="x"
        v-model:y="y"
        v-model:w="w"
        v-model:h="h"
        v-model:r="rotate"
        v-model:active="active"
        :draggable="true"
        :resizable="true"
        @activated="print('activated')"
        @deactivated="print('deactivated')"
        @drag-start="print('drag-start')"
        @resize-start="print('resize-start')"
        @dragging="print('dragging')"
        @resizing="print('resizing')"
        @drag-end="print('drag-end')"
        @resize-end="print('resize-end')"
        @rotating="print('rotating')"
        @rotate-start="print('rotat-start')"
        @rotate-end="print('rotat-end')"
      >
        This is a test example
      </DraggableResizer>
    </div>
  </div>
</template>
```
