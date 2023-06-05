<script>
export default {
    name : "AppMain"

}
</script>

<template>

    <main>

        <div class="cover">

            <select class="dropdown">
            <option value="Alien" selected>Alien</option>
            </select>

        </div>

        <div class="cards-container">

        </div>

    </main>

</template>

<style  lang="scss">
    .main{
        background-color: #d48f38;
        height: calc(100vh - 100px);

        .dropdown{
            padding: 10px;
            background-color: white;
            border: none;
            border-radius: 10px;
            width: 200px;
            margin: 25px;
        }
    }

    .cards-container{
        width: 80%;
        height: 100%;
        margin: auto;
        background-color: white;
    }

</style>
