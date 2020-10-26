<template>
    <div id="app">

        <h3>导航栏</h3>
        <router-link to="/home">留言板</router-link>
        <router-link to="/user">用户表</router-link>
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

</style>
