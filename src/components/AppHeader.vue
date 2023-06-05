<script>
export default {
    name : "AppHeader",
    props: ["msg"]
}
</script>

<template>

<header>
    <div class="img-container">
      <img src="../../public/yugioh_logo.png" alt="yugioh logo">
    </div>
    <h1>{{ msg }}</h1>
</header>

</template>

<style scoped lang="scss">
    header{
      height: 100px;
      display: flex;
      align-items: center;

      .img-container{
        width: 80px;
        margin: 0 25px;
      }
    }
</style>
