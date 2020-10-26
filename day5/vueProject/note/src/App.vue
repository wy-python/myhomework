<template>
    <div id="app">

        <h2 class="h2">导航栏</h2>
        <router-link to="/home"  class="a">留言板</router-link>
        <router-link to="/user"  class="a">用户表</router-link>
        <hr>
        <!--    组件对应内容的显示地址    -->
        <router-view></router-view>
    </div>
</template>

<script>
export default {
    name: 'App'
}
</script>

<style>
.a{
    text-decoration: none;
    color: lightskyblue;
    font-size: 25px;
}
</style>
