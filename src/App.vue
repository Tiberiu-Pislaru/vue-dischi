<template>
  <div id="app">
    <container-disks :disks='listDisks'/>
  </div>
</template>

<script>
import axios from 'axios';
import ContainerDisks from './components/ContainerDisks.vue'

export default {
  name: 'App',
  data(){
    return{
      listDisks:[]
    }
  },
  components: {
    ContainerDisks,
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result)=>{
      console.log(result.data)
      this.listDisks=result.data.response;
    })
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
