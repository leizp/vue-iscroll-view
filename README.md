# vue-iscroll-view

[IScroll](https://github.com/cubiq/iscroll) component for Vue 2.0

## Install

```bash
$ npm i vue-iscroll-view
$ npm i iscroll
```

```javascript
import IScrollView from 'vue-iscroll-view'

/* Using these kinds of IScroll class for different cases. */
import IScroll from 'iscroll'
// import IScroll from 'iscroll/build/iscroll-infinite.js
// import IScroll from 'iscroll/build/iscroll-probe.js
// import IScroll from 'iscroll/build/iscroll-view.js
// import IScroll from 'iscroll/build/iscroll-zoom.js


Vue.use(IScrollView, IScroll)
```

## Get Start

```vue
<template>
  <iscroll-view class="scroll-view">
    Your contents
  </iscroll-view>
</tempalte>

<style>
.scroll-view {
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  overflow: hidden;
}
</style>
```

## Usage

### Set IScroll options

```vue
<template>
  <iscroll-view :options="{preventDefault: false}">
    Your contents
  </iscroll-view>
</tempalte>
```

### Listen IScroll events

```vue
<template>
  <iscroll-view @scrollStart="log">
    Your contents
  </iscroll-view>
</tempalte>

<script>
export default {
  methods: {
    log (iscroll) {
      console.log(iscroll)
    }
  }
}
</script>
```

### Call IScroll instance functions

```vue
<template>
  <div>
    <iscroll-view ref="iscroll">
      Your contents
    </iscroll-view>
    <button @click="scrollToTop">Scroll To Top</button>
  </div>
</tempalte>

<script>
export default {
  methods: {
    scrollToTop () {
      const iscroll = this.$refs.iscroll
      iscroll.scrollTo(0, 0, 100)
      iscroll.refresh()
    }
  }
}
</script>
```

### Custom events

- pullUp
- pullDown

```vue
<template>
  <iscroll-view @pullUp="refresh", @pullDown="load">
    Your contents
  </iscroll-view>
</tempalte>

<script>
export default {
  methods: {
    refresh (iscroll) {
      // Refresh current data
    },
    load (iscroll) {
      // Load new data
    }
  }
}
</script>
```
