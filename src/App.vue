<template>
  <div id="app">
      <headers/>
    <!-- 路由切换的容器 -->
    <router-view></router-view>
  </div>
</template>

<script>
import Headers from "./components/Headers";
export default {
  name:"app",
  data(){
    return{
    }
  },
  components:{
    headers:Headers
  },
    methods:{
  },
  created(){
  }
}
</script>



<style>
body{ margin: 0; padding: 0;}
</style>
