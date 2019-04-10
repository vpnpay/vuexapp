<template>
    <div class="headers">
        <h1>待办事项</h1>
        <div id="nav">
            <router-link to="/home"> 主页</router-link>
            <router-link to="/about"> 关于我们</router-link>
        </div>
    </div>
</template>
<script>
export default {
    name:"headers"
}
</script>
<style scoped>
.headers{ background: #000; padding: 20px; color: #999;}
</style>

