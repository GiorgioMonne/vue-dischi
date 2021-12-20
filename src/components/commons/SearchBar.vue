<template>
    <form class="sarch-bar">
        <input v-model="search" type="text" placeholder="Parola da cercare">
        <button class="sinistro" @click.prevent="$emit('searching',search)">Cerca</button>
        <button class="destra" @click.prevent="$emit('searching',search)">Resetta</button>
    </form>
</template>

<script>
export default {
    name: 'SearchBar',
    data(){
        return{
            search: ""
        }
    }
}
</script>

<style lang="scss" scoped>

    .search-bar{
        .destra{
            border-radius: 2rem;
            background-color: lightcoral;
        }
        .sinistro{
            margin: 10px;
            background-color: lightgreen;  
            border-radius: 2rem;
        }
    }

</style>