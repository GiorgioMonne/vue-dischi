<template>
    <header>
        <div class="logo">
            <img src="../../assets/img/spotify.png" alt="">
        </div>
    </header>    
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>

    header{
        background-color: rgb(66, 66, 90);
    }

    .logo{
        height: 50px;
        width: 100%;
        display: flex;
        align-items: center;

        img{
            height: 30px;
            margin: 0 15px;
            cursor: pointer;
        }
    }

</style>