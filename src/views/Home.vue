<template>
  <div id="app">
    <addtodos v-on:handleAdd="handleAdd"/>
    {{msg}} 
    <todos v-bind:todos="todos" v-on:handleDelete="handleDelete" />
    <helloworld/>
  </div>
</template>

<script>
import Todos from "../components/Todos";
import HelloWorld from "../components/HelloWorld";
import AddTodos from "../components/AddTodos";
import axios from "axios";
export default {
  name:"home",
  data(){
    return{
      msg:"hello",
      todos:[
        
      ]
    }
  },
  components:{
    todos:Todos,
    helloworld:HelloWorld,
    addtodos:AddTodos
  },
    methods:{
        handleDelete(id){
            //this.todos = this.todos.filter(todo=>todo.id !== id);
            axios.delete(`http://jsonplaceholder.typicode.com/todos/${id}`)
            .then(res => this.todos = this.todos.filter(res=>res.id !== id) )
            .catch();

        },
        handleAdd(newTodo){
          //this.todos = [...this.todos,newTodo];
          //this.todos.unshift(newTodo);
          const { title , completed } = newTodo;
          axios.post("http://jsonplaceholder.typicode.com/todos",{
            title,completed
          })
          .then(res=>{this.todos = [res.data, ...this.todos ]})
          .catch();
        }
  },
  created(){
    //数据请求
    axios.get("http://jsonplaceholder.typicode.com/todos?_limit=10")
    .then(res => {
      this.todos = res.data;
    })
    .catch();
  }
}
</script>



<style>
body{ margin: 0; padding: 0;}
</style>
