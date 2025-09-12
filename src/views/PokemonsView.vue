<script setup>
import axios from "axios";
import {ref} from "vue";
import { RouterLink } from "vue-router";
import LoadingSpinner from '../components/LoadingSpinner.vue'
import HeaderComponent from "@/components/HeaderComponent.vue";

const cargando = ref(true);


const pokemons = ref([]);

const GetDate = async () => {
    try{
        const { data } = await axios.get('https://pokeapi.co/api/v2/pokemon'); //?limit=100000&offset=0
        pokemons.value = data.results;
    }
    catch (error) {
        console.log(error);
    }
    finally {
        setTimeout(() => {
            cargando.value = false;
        }, 1500);
    }
}
GetDate();
</script>

<template>
    <div>
        <h1>Pokemons</h1>
        <div v-if="cargando">
            <LoadingSpinner/>
        </div>
        <ul v-else>
            <li v-for="(pokemon,index) in pokemons" :key="index">
                <RouterLink :to="`/pokemons/${pokemon.name}`">
                    {{pokemon.name}}                
                </RouterLink>
            </li>
        </ul>
    </div>
</template>

