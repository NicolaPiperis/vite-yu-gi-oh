<script>
import { store } from './../store.js';
import singleCard from './singleCard.vue';
export default {
    name : "AppMain",
    components : {
        singleCard
    },
    data() {
        return{
            store
        }
    }

}
</script>

<template>

    <main>

        <div class="cover">

            <select class="dropdown" v-model.trim="store.selectArchetype">
            <option :value="store.selectArchetype" selected>{{ store.selectArchetype }}</option>
            <option v-for="(archetype, index) in store.archetypesList" :key="index" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
            </select>

            <button @click.prevent="$emit('mysearch')">Cerca</button>

            <div class="cards-container">

                <div class="el-found">
                    <strong>Found {{ store.cardList.length }} cards</strong>
                </div>

                <div class="riga">
                    <singleCard v-for="card in store.cardList" :key="card.id" :details="card"/>
                </div>
    
            </div>

        </div>


    </main>

</template>

<style  lang="scss">
    .cover{
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

        .cards-container{
            width: 80%;
            height: calc(100% - 100px);
            margin: auto;
            background-color: white;
            padding: 50px 25px;
            overflow: auto;

            .el-found{
                background-color: #212529;
                color: white;
                width: 100%;
                height: 70px;
                font-size: 20px;
                display: flex;
                align-items: center;
                padding-left:10px ;
            }

            .riga{
                display: flex;
                flex-wrap: wrap;
            }
        }
    }


</style>
