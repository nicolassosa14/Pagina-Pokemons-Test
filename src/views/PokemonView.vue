<template>
        <div v-if="cargando">
            <LoadingSpinner />
        </div>
        <div v-else-if="status == 404" class="text-center mt-3"> 
            <h1 class="text-danger">
                Pokemon No Encontrado
            </h1>
            <button @click="back" class="btn btn-outline-danger">Volver</button>
            
        </div>
        <div v-else class="text-center mt-3">

            <img class="img-thumbnail" :src="sprite" alt="imagen pokemon">
            <h1 >{{ $route.params.name }}</h1>
            <button @click="back" class="btn btn-outline-primary">Volver</button>
            <div>
                <!-- <h3>Habilidades</h3>
                <p v-for="habilidad in pokemon">
                    {{ habilidad }}
                </p> -->
            </div>
        </div>
</template>

<script setup>
    import axios from 'axios'
    import {ref} from 'vue'
    import { useRoute, useRouter } from 'vue-router'
    import LoadingSpinner from '../components/LoadingSpinner.vue'


    const cargando = ref(true);

    const router = useRouter();

    const back = () =>{
        router.push("/pokemons")
    }

//const pokemon = ref({})
    const status = ref(0)
    const sprite = ref({})
    const route = useRoute();
    const GetDate = async () => {
        try{
            const { data } = await axios.get(`https://pokeapi.co/api/v2/pokemon/${route.params.name}`); //?limit=100000&offset=0
            //pokemon.value = data.abilities;
            sprite.value = data.sprites?.front_default;
            console.log(data);
            status.value = 200; // Assuming a successful fetch means status 200
        }
        catch (error) {
            console.log(error);
            status.value = 404
        }finally {
        setTimeout(() => {
            cargando.value = false;
        }, 1500);
    }
    }
    GetDate();

</script>