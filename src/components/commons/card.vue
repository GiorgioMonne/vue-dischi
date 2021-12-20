<template>
    <main>
        <div class="search-bar">
                <SearchBar @searching="CercaRobe"/>
        </div>
        <div class="search-bar">
                <SearchBar/>
        </div>
        <div class="search-bar">
                <SearchBar/>
        </div>

        <div class="container-card">         
            <div class="card" v-for="(card, index) in cards" :key="index">
                <img :src="card.poster" alt="">
                <div class="testo">
                    <h2>{{card.title}}</h2>
                    <h4>{{card.author}}</h4>
                    <h4>{{card.year}}</h4>
                </div>
            </div>
            <!-- <div class="loader"  v-if=" loader == false ">
                LOADING...
            </div> -->
        </div>
    </main>
</template>

<script>

import axios from 'axios';
import SearchBar from '../commons/SearchBar.vue';

export default {
    name: 'card',
    components: {
        SearchBar
    },
    data(){
        return{
            cards: null
            // loader: false
        }
    },
    created(){
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            this.cards = response.data.response;
            // this.loader = true;
        })
        .catch(function (error){
            console.log(error);
        });        
    },
    methods:{
        CercaRobe(payload){
            console.log(payload);
        }
    }

}
</script>

<style lang="scss" scoped>

    main{
        background-color: rgb(33, 39, 90);
        padding: 55px 0;
        
    }

    h2{
        text-align: center;
        text-transform: uppercase;
        color: white;
    }

    h4{
        color: grey;
    }

    .search-bar{
        display: flex;
        justify-content: center;
        margin-bottom:20px;
    }

    .container-card{
        margin:0 auto;
        max-width: 1200px;
        background-color: rgb(21, 55, 63);
        display: flex;
        flex-wrap: wrap;
        padding: 40px 0;
        
        .card{
            display: flex;
            flex-direction: column;
            width: calc(235px - 10px);
            margin: 5px;
            background-color: rgba(128, 128, 128, 0.555);
            text-align: center;
            margin: 20px auto;
            opacity: 0.8;
            cursor: pointer;
        }

        .card:hover{
            opacity: 1;
        }

        img{
            width: 85%;
            margin: 20px auto;
            object-fit: cover;
        }

        .testo{
            width: 85%;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
        }
    }


</style>