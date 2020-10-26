<template>
    <div>
        <h3>留言板</h3>
        <hr>
        <input type="text" v-model="msg">
        <button @click="add_note">添加留言</button>
        <ul>
            <li v-for="(note, index) in msg_list" :key="index">{{ note }}
                <a href="javascript:;" @click="delNote(index)">删除</a>
            </li>
        </ul>

        <span>留言总条数:{{msg_list.length}}</span>
        <input type="button" value="删除所有" @click="delete_all" v-show="isShow">
    </div>
</template>

<script>
export default {
    name: "Home",
    data:
        function () {
        return {
            msg: "",
            isShow:true,
            // 按段localStorage是否有值  有值则显示 如果没有 则设置成空数组
            msg_list: localStorage.msgs ? JSON.parse(localStorage.msgs) : [],
        }
    },
    methods: {
        // 删除留言
        delNote(index){
            console.log(index);
            // 根据下标取删除某个元素
            this.msg_list.splice(index, 1);
            if (this.msg_list.length == 0){
                this.isShow = false;
            }
        },
        //删除全部留言
        delete_all(){
            this.msg_list = [];
            this.isShow = false;
        },
        add_note() {
            let msg = this.msg;
            if (msg) {
                // 将用户发表的留言储存到localstorage
                // 储存前将数据进行序列化
                this.msg_list.push(this.msg);
                localStorage.msgs = JSON.stringify(this.msg_list);
                this.msg = "";
            }

        },
    }
}
</script>

<style scoped>

</style>
