<template>
    <form>
        <label for="select">Filter By Gender</label>
        <select @change="$emit('selectedGenre', select)" v-model="select">
            <option>All</option>
            <option v-for="(genre,index) in genreList" :key="genre + index">{{genre}}</option>
        </select>
    </form>
</template>

<script>
export default {
    name: 'SelectGenre',

    data(){
        return{
            genreList: ['Rock', 'Pop', 'Jazz', 'Metal',],
            select: 'All',
        }
    },
}

</script>

<style lang='scss' scoped>
@import '@/components/scss/var';

form{
    label{
        color: white;
        margin-right: 10px;
    }

    select{
        width: 150px;
        padding: 2px;
    }
}

</style>