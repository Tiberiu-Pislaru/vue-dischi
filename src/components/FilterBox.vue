<template>
    <div class="container-select">
        <label for="cars">Choose a genre:</label>

        <select name="cars" id="cars" v-model="selected" 
        @change="$emit('search',selected)">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="pop">Pop</option>
            <option value="jazz">Jazz</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    data(){
        return{
            selected:'all'
        }
    }
}
</script>

<style lang="scss" scoped>

</style>