<template>
    <div class="single-card">    
        <div class="artist-image">
            <img :src="details.poster" :alt="details.title">
        </div>
        <div class="song-name">
            {{details.title}}
        </div>
        <div class="artist-name">{{details.author}}</div>
        <div class="song-date">{{details.year}}</div>
    </div>
</template>

<script>
export default {
    name: "SingleCard",
    props: {
        details: Object
    }
}
</script>

<style scoped lang="scss">
@import '../style/generals.scss';

.single-card{
    width: calc((100% / 5) - 40px);
    margin: 0 20px;
    background-color: $brand-primary-color;
    padding-top: 20px;
    padding-bottom: 60px;
    text-align: center;
    height: 400px;
    .artist-image{

        img{
            height: 150px;
            width: 150px;
        }
    }

    .song-name{
        color: white;
        font-size: 20px;
        text-transform: uppercase;
        padding-top: 20px;
        padding-bottom: 30px;
        width: 80%;
        margin: auto;
    }

    .artist-name,
    .song-date{
        color: #726f6a;
        font-size: 18px;
    }
}

</style>
