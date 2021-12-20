<template>
    <main>
        <card/>  
    </main>
</template>

<script>

import card from '../commons/card.vue';
export default {
    name: 'Main',
    components:{
        card
    }
}
</script>

<style lang="scss" scoped>

    main{
        background-color: rgb(33, 39, 90);
        
    }

    .container{
        display: flex;
        flex-wrap: wrap;
    }

</style>