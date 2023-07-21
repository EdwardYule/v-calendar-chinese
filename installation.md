---
title: 'Installation'
---

:::提示
需要[Vue.js](https://vuejs.org) 2.5或以上版本。
:::

## NPM

### 1. 通过npm安装

```bash
npm install v-calendar
```

### 2. 导入并使用 VCalendar
#### *2A. 以插件方式使用 (推荐的使用方法)*

通过插件方式，将同时引入<v-calendar>和<v-date-picker>两个组件。以下是一个最常见的例子。

```js
import Vue from 'vue';
import VCalendar from 'v-calendar';

// 使用 v-calendar 和 v-date-picker 组件
Vue.use(VCalendar, {
  componentPrefix: 'vc',  // 使用 <vc-calendar /> 来代替 <v-calendar />
  ...,                // ...其他配置
});

```

#### *2B. 以组件方式使用*

如果你不想以插件方式使用，那么你也可以分别引入组件后再注册。

```js
import Calendar from 'v-calendar/lib/components/calendar.umd'
import DatePicker from 'v-calendar/lib/components/date-picker.umd'

// 在'main.js'中注册全局组件
Vue.component('calendar', Calendar)
Vue.component('date-picker', DatePicker)

// 或者就注册在某个Vue组件中
export default {
  components: {
    Calendar,
    DatePicker
  }
  ...
}
```

If you would still like to provide [plugin defaults](../api/defaults.md), call `setupCalendar` before using any components.

```js
import { setupCalendar} from 'v-calendar'

// main.js
setupCalendar({
  componentPrefix: 'vc',
  ...,
});
```

## CDN
```html
<html>
  <head>
    <meta charset='utf-8'>
    <meta name='viewport' content='width=device-width, initial-scale=1, shrink-to-fit=no'>
    <meta http-equiv='x-ua-compatible' content='ie=edge'>
    <!-- IMPORTANT: No CSS link needed as of v1 - It's all inlined -->
    <!-- Pre v1.0.0 versions need the minified css -->
    <!-- <link rel='stylesheet' href='https://unpkg.com/v-calendar/lib/v-calendar.min.css'> -->
  </head>
  <body>
    <div id='app'>
      <v-calendar></v-calendar>
      <v-date-picker v-model='selectedDate' />
    </div>

    <!-- 1. Link Vue Javascript -->
    <script src='https://unpkg.com/vue/dist/vue.js'></script>

    <!-- 2. Link VCalendar Javascript (Plugin automatically installed) -->
    <script src='https://unpkg.com/v-calendar'></script>

    <!--3. Create the Vue instance-->
    <script>
      new Vue({
        el: '#app',
        data: {
          selectedDate: null,
        }
      })
    </script>
  </body>
</html>
```