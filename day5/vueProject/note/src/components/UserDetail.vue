<template>
    <div>
        <h3>这里是用户详情页</h3>
        <hr>
<!--        <h4>用户ID为: {{$route.params.id }}</h4>-->
        <h4>用户ID为: {{ id }}</h4>
        <br>
        <h4>用户名为:  {{ username }}</h4>
<!--        <h4>用户名为:  {{$route.params.username}}</h4>-->
    </div>
</template>

<script>
export default {
    name: "UserDetail",
    data:function () {
        return{
            id:"",
            username:"",
        }
    },
    methods:{
     },
    created() {
        // console.log("create: " + this.$route.params.id)
        this.id=this.$route.params.id
        // console.log("create: " + this.$route.params.username)
        this.username = this.$route.params.username

    }
    }

</script>

<style scoped>

</style>
