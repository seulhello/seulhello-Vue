<template>
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo" placeholder="Type Here">
        <span class="addContainer" v-on:click="addTodo"><i class="addBtn fa fa-plus"></i></span>
    </div>
</template>
<script>
    export default{
        data(){
            return{
                newTodoItem:''
            }
        },
        methods:{
            addTodo(){
                if(this.newTodoItem !== ""){
                    var value = this.newTodoItem && this.newTodoItem.trim();
                    // localStorage.setItem(value,value);
                    this.$emit('addTodo',value);
                    this.clearInput();
                }
            },
            clearInput(){
                this.newTodoItem = '';
            }
        }
    }
</script>
<style scoped>
input:focus{outline:none;}
.inputBox{height:50px;background:#fff;line-height:50px;border-radius:50px;}
.inputBox input{font-size:0.9rem;border-style:none;}
.addContainer{float:right;width:3rem;background:linear-gradient(to right, #6478fb,#8763fb);}
.addBtn{color:#fff;vertical-align:middle;}
</style>


