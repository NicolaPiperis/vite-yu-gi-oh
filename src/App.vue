<script>
import axios from 'axios';
import { store } from './store.js'
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
    components: {
      AppHeader,
      AppMain
    },
    data() {
        return{
            store
        }
    },
    methods : {
        getCards () {
            axios.get(store.apiURL)
            .then(res => {
                store.cardList = res.data.card_images;
            })
            .catch(err =>{
                console.log(err);
            })
        }
    },
    created() {
        this.getCards();
    }
}
</script>

<template>
    <AppHeader msg="Yu-Gi-Oh Api" />

    <AppMain />
</template>

<style lang="scss">
@use './styles/general.scss' as *;
</style>
