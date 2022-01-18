<template>
<select v-model="genreSelect" name="genre" id="genre" class="form-select" @change="$emit('doSelect', genreSelect)">
<option value="all">All</option>
<option value="rock">Rock</option>
<option value="pop">Pop</option>
<option value="jazz">Jazz</option>
<option value="metal">Metal</option>
</select> 
</template>

<script>
export default {
    name: "Search",
    data () {
        return {
            genreSelect: "all"
        }
    }
}
</script>

<style>

</style>