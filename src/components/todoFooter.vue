<template>
    <div class="clearAllContainer">
        <span class="clearAllBtn" @click="clearTodo()">Clear All</span>
    </div>    
</template>
<script>
    export default{
        methods:{
            clearTodo(){
                this.$emit('removeAll');
            }
        }
    }
</script>
<style scoped>
.clearAllContainer{width:8.5rem;height:50px;margin:0 auto;background-color:#fff;line-height:50px;border-radius:5px;}
.clearAllBtn{display:block;color:#e20303;}
</style>


