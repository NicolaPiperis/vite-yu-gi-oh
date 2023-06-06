<script>
export default {
    name : "singleCard",
    props: {
        details: Object 
    }

}
</script>

<template>

    <div class="card">

        <!-- <img v-for="image in details.card_images" :src="image.image_url" alt="info.image"> -->
        <img :src="details.card_images[0].image_url" alt="info image">

        <div class="name">{{ details.name }}</div>

        <div class="species">{{ details.archetype }}</div>
    </div>
    
</template>

<style scoped lang="scss">

    .card{
        height: 500px;
        background-color: #d48f38;
        margin-top: 0;
        margin-bottom: 30px;
        margin-left: 25px;
        margin-right: 25px;
        width: calc((100% / 5) - 50px);

        .name{
            font-size: 18px;
            font-weight: 800;
            color: white;
            padding: 10px;
            text-align: center;
        }

        .species{
            text-align: center;
        }

        img{
            height: 300px;
        }
    }

</style>
