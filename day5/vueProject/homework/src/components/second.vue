<template>

  <div>
    <p>这是我的第二个组件</p>

    <h3>这里是我的名字:{{ username }}</h3>

    <span @click="change">今年是抗美援朝{{ number }}周年</span>

  </div>


</template>

<script>
export default {
  name: "second",
  data: function () {
    return {
      username: "武毅",
      number: 70,
    }
  },
  methods: {
    change() {
      this.number --;
    },
  }
}
</script>

<style scoped>
span {
  color: red;
}
</style>
