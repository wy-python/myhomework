<template>
    <div>
        <input type="text" v-model="msg">
        <button @click="add_note">添加留言</button>

        <ul>
            <li v-for="(note, index) in msg_list" :key="index">{{ note }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Home",
    data: function () {
        return {
            msg: "",
            // 按段localStorage是否有值  有值则显示 如果没有 则设置成空数组
            msg_list: localStorage.msgs ? JSON.parse(localStorage.msgs) : [],
        }
    },
    methods: {
        add_note() {
            let msg = this.msg;
            if (msg) {
                this.msg_list.push(this.msg);
                // 将用户发表的留言储存到localstorage
                // 储存前将数据进行序列化
                localStorage.msgs = JSON.stringify(this.msg_list);
                this.msg = "";
            }
        },
    }
}
</script>

<style scoped>

</style>
