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
            let myurl = store.apiURL;

            if(store.selectArchetype !== "") {
                myurl += `?${store.apiArchetypeParameter}=${store.selectArchetype}`
            }

            axios.get(store.apiURL)
            .then(res => {
                store.cardList = res.data.data;
            })
            .catch(err => {
                console.log(err);
            })
        },
        getArchetypes () {
            axios.get(store.apiArchetypeUrl)
            .then(resA => {
                store.archetypesList = resA.data;
            })
        }
    },
    created() {
        this.getCards();
        this.getArchetypes();
    }
}
</script>

<template>
    <AppHeader msg="Yu-Gi-Oh Api" />

    <AppMain @mysearch="getCards" />

    
</template>

<style lang="scss">
@use './styles/general.scss' as *;
</style>
