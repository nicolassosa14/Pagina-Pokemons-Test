<script setup>
import 'bootstrap/dist/css/bootstrap.min.css';
import 'bootstrap/dist/js/bootstrap.bundle.min.js';
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
import { ref } from 'vue';
import HeaderComponent from './components/HeaderComponent.vue';

</script>

<template>
    <HeaderComponent/>
  <div class="contenedor">

    <RouterView />
  </div>
</template>

<style>

.contenedor {
  display: block;
  margin: 15px;
}
</style>
