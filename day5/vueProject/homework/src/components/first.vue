<!--组件的template 内部只能有一个根标签-->
<template>

  <!--  template只能有一个根标签  -->
  <div>
    这是我的第一个组件:)
    <br>
    <span>Vue那是真的好用,老师的课是真的好懂</span>
    <h3>我觉得你说的对</h3>
  </div>

</template>

<!--编写js代码的地方  当前对象就是组件对象-->
<script>
// 将组件导出
export default {
  name: "First"
}
</script>

<!--当前组件的样式 scoped: 脚手架提供的属性 加上此属性代表当前样式只在此组件中生效-->
<style scoped>

div {
  color: pink;
}

span {
  color: yellow;
}

</style>
