<template>
    <header>
        <img src="@/assets/img/logo.png" alt="">
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style scoped lang="scss">
@import '@/components/scss/var';

header{
    padding: 5px;
    background-color: $semi-trasparent;

    img{
        max-width: 45px;
    }
}
</style>
