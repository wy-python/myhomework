<template>

    <div>
        这是User组件
        <h3>用户列表页</h3>
        <table border="2">
            <tr>
                <td>ID</td>
                <td>姓名</td>
                <td>生日</td>
                <td>个人信息</td>
                <td>操作</td>
            </tr>
            <tr v-for="user in users" :key="user.id">
                <td>{{ user.id }}</td>
                <td>{{ user.username }}</td>
                <td>{{ user.bir }}</td>
                <td>{{ user.content }}</td>
                <td>删除 |
                    <router-link :to="`/detail/${user.id}`">查看用户详情</router-link>
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
                {"id": 1, username: "小黑", bir: "2012-12-12", content: '我是小黑'},
                {"id": 2, username: "小包", bir: "2013-10-12", content: '我是小包'},
                {"id": 3, username: "小李", bir: "2014-11-12", content: '我是小李'},
            ],
            username: "",
            bir: "",
            content: "",
        }
    },
    methods: {
        addUser() {
            // 获取到三个用户信息
        },

    }
}
</script>

<style scoped>

</style>
