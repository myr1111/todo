<template>
      <form v-on:submit.prevent="add()">
                <div class="form-group">
                    <input v-model="newTodo.title" type="text" placeholder="请输入您想要做的事" class="form-control">
                </div>
                <div class="form-group">
                    <button type="submit" class="btn btn-success">添加</button>
                </div>
            </form>
</template>

<script>
    export default{
        props:["todos"],
        data(){
            return{
                newTodo:{title:"",status:false}
        }
    },
     methods:{
            add(){
                this.todos.push(this.newTodo)
               this.newTodo={title:"",status:false}
           }
        }
    }
</script>
<style>

</style>