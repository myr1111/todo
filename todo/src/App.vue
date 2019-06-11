<template>
  <div id="app">
    <todos :todos="todos"></todos>
    <todo-form :todos="todos"></todo-form>
  </div>
</template>

<script>
import Todos from './components/Todos'
import TodoForm from './components/TodoForm'

export default {
  name: 'app',
  data(){
    return{
           todos:[
                {title:"aaaaa",status:false},
                {title:"bbbbb",status:false}
           ]
       }
  },
          components:{
            Todos,TodoForm
          },
          computed:{
            todoCount:function(){
                return this.todos.length
            }
       }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
