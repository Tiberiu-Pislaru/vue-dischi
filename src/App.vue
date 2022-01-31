<template>
  <div id="app">
    <container-logo/>
    <container-disks :disks='listDisks'/>
  </div>
</template>

<script>
import axios from 'axios';
import ContainerDisks from './components/ContainerDisks.vue'
import ContainerLogo from './components/ContainerLogo.vue'

export default {
  name: 'App',
  data(){
    return{
      listDisks:[]
    }
  },
  components: {
    ContainerDisks,
    ContainerLogo,
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result)=>{
      
      this.listDisks=result.data.response;
    })
  }
}
</script>

<style lang="scss">
@import './style/MainStyle.scss'

</style>
