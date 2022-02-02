<template>
    <div class="container-disk">
        <div class="disk-body" v-for="(disk,index) in disks" :key="index">
           
            <disk-box :disk='disk'/>
            
        </div>
    </div>
</template>

<script>
import DiskBox from './DiskBox.vue'
export default {
    components: {
        DiskBox
    },
    props:{
        disks:Array
    }
}
</script>

<style lang="scss" scoped>
.container-disk{
   
    width: 950px; 
    margin: 0 auto;
    display: flex;
    flex-wrap: wrap;
    // justify-content: space-around;
    
    
    .disk-body{
        text-align: center;
        width: calc(100% / 5 - 20px);
        margin: 0 10px;
        margin-bottom: 15px;
        padding: 15px;
        background-color:#2E3A46;
    }
}
</style>