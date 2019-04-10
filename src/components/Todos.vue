<template>
    <div>
        <p v-bind:key="index" v-for="(todo,index) in todos"> 
            <todo v-bind:todo="todo" v-on:deleteItem="$emit('handleDelete',todo.id)" />
        </p>
        
    </div>
</template>
<script>
import TodoItem from "./TodoItem";
export default {
    name:"todos",
    props:{
        todos:{
            type:Array
        }
    },
    components:{
        todo:TodoItem
    }
}
</script>
<style scoped>

</style>
