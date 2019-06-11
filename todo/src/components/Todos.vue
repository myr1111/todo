<template>
     <ul class="list-group">
                <li class="list-group-item"
                    v-bind:class="{'finsh' : todo.status}"
                    v-for="(todo,index) in todos"
                >{{todo.title}}
                    <button @click="del(index)" class="btn btn-danger btn-xs pull-right">删除</button>
                    <button 
                        @click="status(todo)" 
                        :class="[todo.status?'btn-warning':'btn-success']"
                        class="btn btn-success btn-xs pull-right"
                        >
                        {{todo.status?'未完成':'完成'}}
                    </button>
                </li>
            </ul>
</template>

<script>
    export default{
         props:["todos"],
         methods:{
           del(index){
               this.todos.splice(index,1);
           },
           status(todo){
                todo.status=!todo.status;
           }
        }
    }
</script>
<style>
.finish{
            color:chartreuse;
            text-decoration: line-through;
        }
</style>
