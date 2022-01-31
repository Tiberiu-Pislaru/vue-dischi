<template>
    <div >

        <div class="img-box">
            <img :src="disk.poster" alt="">
        </div>
        <div class="name">
            {{disk.name}}
        </div>
        <div class="origin">
            {{disk.origin}}
        </div>
        <div class="type">
            {{disk.type}}
        </div>
        

    </div>
</template>

<script>
export default {
    props: {
        disk:Object
    }
}
</script>

<style lang="scss" >
// .container-box {
    // display: flex;
    // flex-wrap: wrap;
    // justify-content: space-around;
    // width: 950px; 
    // margin: 0 auto;
    // text-align: center;

    
// width: calc(100% / 4 - 20px);
// margin-bottom: 15px;
.img-box {
    
    // background: red;
    overflow: hidden;
    border-radius: 50%;
    // margin-bottom: 10px;
    // width: 100%;
    

    img{
        width: 100%;
        // object-fit: cover;
    
    }
}
.name{
    padding-bottom: 15px;
    border-bottom: 2px solid grey;
    margin-bottom:15px
}
.type{
    font-weight: bold;
}
    
// }
</style>