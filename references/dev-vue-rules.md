若我没有明确某条要求，遵守下属规定。

# 总约定

- 写新代码时，VueSFC 使用 Composition API，除非是老的 Option API 项目
- SFC 块的顺序优先级是：`<template>`、`<script setup lang='ts'>`、`<style>`
- `defineProps`、`defineEmits` 等 Vue 编译宏直接使用不要导入
- 组件优先使用 `.vue`（SFC），仅无响应式副作用、无生命周期副作用的轻量组件可由 `.ts` 直接导出，其它情况使用 `.tsx`

## 模块拆分

- `<template>` 超过 50 行或者已经包含了多个独立的业务内容时，优先拆出子组件
- 父子组件优先使用 props、emits 通信；跨层级共享能力可以使用 `provide` + `inject`
- 不使用 `watch`、`watchEffect` 充当组件间的消息通道，响应式副作用只处理无法由事件或明确调用表达的状态联动
- 拆分粒度以业务功能为单位，不为单个普通控件创建组件

## 业务编排

- 单个 SFC 的脚本区域平铺超过 3 类业务职责时，优先抽离 composable，或者由全局状态 pinia 集成
  - “3类”是重构提示，不是硬性要求，目标是避免逻辑堆积
- 上层编排组件只负责生命周期、依赖装配、业务流程
