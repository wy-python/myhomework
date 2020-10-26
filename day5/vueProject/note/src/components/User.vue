<template>

    <div>
        <h3>用户详情页</h3>
        <table border="1">
            <tr>
                <td>ID</td>
                <td>姓名</td>
                <td>生日</td>
                <td>个人信息</td>
                <td>操作</td>
            </tr>
            <tr v-for="(user,index) in users" :key="user.id">
                <td>{{ index+1}}</td>
                <td>{{ user.username }}</td>
                <td>{{ user.bir }}</td>
                <td>{{ user.content }}</td>
                <td><a href="javascript:;" @click="delUser(index)">删除</a> |
                    <router-link :to="`/detail/${index+1}/${user.username}`">查看用户详情</router-link>
                </td>
            </tr>
        </table>

        <hr>
        用户名: <input type="text" v-model="username"><br>
        生日: <input type="text" v-model="bir"><br>
        个人信息: <input type="text" v-model="content"><br>
        <button @click="addUser">添加用户</button>

    </div>

</template>

<script>
export default {
    name: "User",
    data() {
        return {
            users: [
                {"id": 1, username: "武毅", bir: "2000-01-01", content: '我是天桥武毅'},
                {"id": 2, username: "铁鑫", bir: "2000-10-10", content: '我是厦大铁鑫'},
                {"id": 3, username: "龙哥", bir: "2012-12-12", content: '我是昆山龙哥'},
            ],
            username: "",
            bir: "",
            content: "",
        }
    },
    methods: {
        addUser() {
            let username = this.username;
            let bir =this.bir;
            let content = this.content
            let user={username:username,bir:bir,content:content}
            if (user){
                this.users.push(user);
                user = "";
            }
        },
        delUser(index){
            console.log(index);
            this.users.splice(index,1);

        },
    }
}
</script>

<style scoped>

</style>
