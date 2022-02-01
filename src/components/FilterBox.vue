<template>
    <div class="container-select">
        <label for="cars">Choose a genre:</label>

        <select name="cars" id="cars" v-model="selected" 
        @change="$emit('search',selected)">
            <option value="">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    data(){
        return{
            selected:''
        }
    }
}
</script>

<style lang="scss" scoped>

</style>