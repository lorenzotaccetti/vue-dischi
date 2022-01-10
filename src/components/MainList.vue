<template>
    <div class="main">
        <Select @changeValue="changeFunction" />
        <div class="container">
            <template v-if="filteredValue.length > 0">
                <SingleCard v-for="(element, index) in filteredValue" :key="index" :details="element"/>
            </template>
            <template v-else>
                <div class="no-result">Nessun risultato</div>
            </template>
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
            selectedValue: '',
        };
    },
    methods:{
        changeFunction: function(value){
            this.selectedValue = value;
        }
    },
    computed: {
        filteredValue: function(){
            if(this.selectedValue === ''  || this.selectedValue === 'all'){
                return this.artist
            }

            const filteredArray = this.artist.filter((element) => {
                return element.genre.toLowerCase().includes(this.selectedValue.toLowerCase())
            });

            return filteredArray
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

    .no-result{
        color: white;
        font-size: 20px;
    }
}
</style>