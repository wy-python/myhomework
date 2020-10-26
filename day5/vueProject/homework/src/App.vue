<template>
  <div id="app">

    <First></First>
    <hr>
    <Second></Second>

  </div>
</template>

<script>

// 注册组件时需要先将组件导入过来
import First from "./components/First"
import Second from "./components/Second";

export default {
  name: 'App',
  // 将组件注册到根组件中
  components: {
    First: First,
    Second: Second,
  }
}
</script>

<style>

</style>
