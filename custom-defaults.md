---
title: '自定义默认值'
sidebarDepth: 1
---

### 自定义默认值

在初始化时你可以为`v-calendar`或`v-date-picker`组件提供自定义默认值。不过，几乎所有这些默认值都可以通过组件上的props进行覆盖。

```js
Vue.use(VCalendar, {
  componentPrefix: 'vc', // 现在将使用vc-calendar和vc-date-picker
  ...
})
```

[点我查看所有默认值](../api/v2.0/defaults.md)