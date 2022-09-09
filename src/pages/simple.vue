<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Simple</h1>
        <card class="w-1/2" v-bind="objet" />
    </div>
</template>
    
<script setup lang="ts">
import card from "../components/card.vue";

const objet = { nom: "Maison haute gamme", price: 1150, favoris: true, txt: "maison à vendre", nbbath: 3, nbsize: "250 m²", img: "house.jpg" }
</script>