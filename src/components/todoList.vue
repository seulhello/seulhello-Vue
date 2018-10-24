<template>
    <section>
        <ul>
            <!-- <li v-for="todoItem in todoItems" class="shadow"> -->
            <li v-for="(todoItem,index) in propsdata" class="shadow">
                <i class="checkBtn fa fa-check" aria-hidden="true"></i>
                {{todoItem}}
                <span class="removeBtn" type="button" @click="removeTodo(todoItem,index)">
                    <i class="fa fa-trash-o" aria-hidden="true"></i>
                </span>
            </li>
        </ul>
    </section>
</template>
<script>
    export default{
        props:['propsdata'],
        // data() {
        //     return {
        //     todoItems: []
        //     }
        // },
        // created(){
        //     if (localStorage.length > 0) {
        //         for (var i = 0; i < localStorage.length; i++) {
        //             this.todoItems.push(localStorage.key(i));
        //         }
        //     }
        // },
        methods:{
            removeTodo(todoItem,index){
                localStorage.removeItem(todoItem);
                this.todoItem.splice(index,1);
            }
        }
    }
</script>
<style>
ul{padding-left:0;margin-top:0;text-align:left;list-style-type:none;}
li{display:flex;min-height:50px;height:50px;margin:0.5rem 0;padding:0 0.9rem;background:#fff;line-height:50px;border-radius:5px;}
.checkBtn{margin-right:5px;line-height:45px;color:#62acde;}
.removeBtn{margin-left:auto;color:#de4343;}
</style>


