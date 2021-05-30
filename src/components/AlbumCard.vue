<template>
    <div class="card">
        <img :src="details.poster" :alt="details.title">

        <h2 class="white">{{details.title}}</h2>
        <h3 class="grey">{{details.author}}</h3>
        <h4 class="grey">{{details.year}}</h4>
        <h4 class="white">{{details.genre}}</h4>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',
    props: ['details']
}
</script>

<style scoped lang='scss'>
@import '@/components/scss/var';


.white{
    color: white;
}
.grey{
    color: $default-grey;
}

.card{
    background-color: $semi-trasparent;
    text-align: center;
    width: calc(100% / 6 - 30px);
    height: 380px;
    padding: 20px;
    margin: 15px;

    img{
        width: 150px;
        height: 150px;
        object-fit: cover;
    }

    h2{
        margin: 25px 0 20px;
        font-weight: 400;
        text-transform: uppercase;
        font-size: 20px;
    }

    h3{
        font-size: 18px;
    }

    h3,
    h4{
        line-height: 1.5rem;
        font-weight: 400;
    }

}
@media screen and (min-width: 1600px) {
    .card{
        width: calc(100% / 8 - 30px);
        }
}

</style>