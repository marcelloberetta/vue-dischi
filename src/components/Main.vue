<template>
    <main>
        <div class="container">
            <SelectGenre @selectedGenre="filterGenre" />
            <div class="album-container">
                <AlbumCard
                v-for="(album,index) in filteredAlbums"
                :key="index"
                :details="album"/>
            </div>
        </div>
    </main>
</template>

<script>
import axios from 'axios';
import AlbumCard from '@/components/AlbumCard'
import SelectGenre from '@/components/SelectGenre';

export default {
    name: "Main",

    components:{
        AlbumCard,
        SelectGenre,
    },

    data(){
        return{
            apiURL: 'https://flynn.boolean.careers/exercises/api/array/music',
            albumsList: [],
            actualGenre: 'All',
        }
    },

    computed: {
        filteredAlbums() {
            if( this.actualGenre === "All" ){
                console.log("oi")
                return this.albumsList;
            }else{
                return this.albumsList.filter( e => e.genre === this.actualGenre )
            }
        }
    },

    created() {
        this.getMusicInfo();
    },

    methods: {
        getMusicInfo(){
            axios.get(this.apiURL)
            .then( resp =>{
                this.albumsList = resp.data.response;
            })
        },

        filterGenre(value){
           this.actualGenre = value
           console.log('genere attuale: ', this.actualGenre);
        },

    }
}
</script>


<style lang='scss' scoped>
@import '@/components/scss/var';

main{
    padding: 100px 0;

    .container{

        form{
            text-align: center;
        }

        .album-container{
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 30px;
        }
    
    }
}


</style>