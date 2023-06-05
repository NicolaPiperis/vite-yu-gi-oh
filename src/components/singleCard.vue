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

        <img src="info.image" alt="info.image">

        <div class="name">name</div>

        <div class="species">species</div>
    </div>
    
</template>

<style scoped lang="scss">

    .card{
        height: 400px;
        background-color: #d48f38;
    }

</style>
