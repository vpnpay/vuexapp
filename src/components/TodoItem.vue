<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete"> {{todo.title}}
            <button class="del" v-on:click="$emit('deleteItem',todo.id)">X</button>
        </p>
    </div>
</template>
<script>
export default {
    name:"todo",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>
<style scoped>
.todo-item{ color: red;}
.is-complete{ text-decoration: line-through}
</style>


