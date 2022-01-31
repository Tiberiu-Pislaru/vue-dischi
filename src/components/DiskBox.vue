<template>
    <div class="card" >

        <div class="img-box">
            <img :src="disk.poster" alt="">
        </div>
        <div class="title">
            {{disk.title}}
        </div>
        <div class="author">
            {{disk.author}}
        </div>
        <div class="year">
            {{disk.year}}
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



.img-box {
    display: inline-block;
    img{
        width: 100%;
        height: 100%;
        object-fit: fill;
    }
}

.title{
    color: white;
    font-weight:bold;
    font-size: 20px;
    text-transform: uppercase;
    margin-bottom: 15px;
}

.author,
.year{
    color: #697980;
}

    
</style>