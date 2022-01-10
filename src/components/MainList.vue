<template>
    <div class="main">
        <Select @changeValue="changeFunction" />
        <div class="container">
            <SingleCard v-for="(element, index) in artist" :key="index" :details="element"/>
        </div>
    </div>
</template>

<script>
import SingleCard from './SingleCard.vue';
import Select from './Select.vue';
import axios from 'axios';

export default {
    name: "MainList",
    components: {
        SingleCard,
        Select,
    },
    data: function(){
        return{
            artist: [],
        };
    },
    methods:{
        changeFunction: function(value){
            console.log(value)
        }
    },
    created: function(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.artist = response.data.response
            console.log(this.artist)
        })
    }
}
</script>

<style scoped lang="scss">
@import '../style/generals.scss';

.main{
    background-color: $brand-secondary-color;

    .container{
        height: 100vh;
        width: 70%;
        margin: auto;
        display: flex;
        // align-items: center;
        flex-wrap: wrap;
    }
}
</style>