<template>
  <div id="app">
    <container-logo :check='listDisks'/>
    <container-disks :disks='listDisks' />
    <loader-box v-if="this.listDisks.length===0"/>
  </div>
</template>

<script>
import axios from 'axios';
import ContainerDisks from './components/ContainerDisks.vue'
import ContainerLogo from './components/ContainerLogo.vue'
import LoaderBox from './components/LoaderBox.vue'

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
    LoaderBox
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result)=>{
      console.log(result.data.response.length)
      this.listDisks=result.data.response;
    })
  }
}
</script>

<style lang="scss">
@import './style/MainStyle.scss'

</style>
