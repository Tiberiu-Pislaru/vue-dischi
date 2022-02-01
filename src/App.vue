<template>
  <div id="app">
    <container-logo :check='listDisks'/>
    <filter-box @search='alertTry'/>
    <loader-box v-if="!loaded"/>
    <container-disks v-else :disks='filteredDisks' />
  </div>
</template>

<script>
import axios from 'axios';
import ContainerDisks from './components/ContainerDisks.vue'
import ContainerLogo from './components/ContainerLogo.vue'
import LoaderBox from './components/LoaderBox.vue'
import FilterBox from './components/FilterBox.vue'

export default {
  name: 'App',
  data(){
    return{
      listDisks:[],
      filteredDisks:[],
      loaded:false
    }
  },
  components: {
    ContainerDisks,
    ContainerLogo,
    LoaderBox,
    FilterBox
  },
  methods:{
    alertTry(string){
      this.filteredDisks=this.listDisks.filter((disk)=>{
        return disk.genre.toLowerCase().includes(string.toLowerCase())
      })
    }
  },
  mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((result)=>{
      console.log(result.data.response.length)
      this.listDisks=result.data.response;
      this.filteredDisks=result.data.response;
      this.loaded=true;
    })
  }
}
</script>

<style lang="scss">
@import './style/MainStyle.scss'

</style>
