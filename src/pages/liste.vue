<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="maisons in maisons" :key="maisons.nom">
            <card class="w-1/2" v-bind="maisons" />
        </div>
    </div>
</template>

<script setup lang="ts">
import card from "../components/card.vue";

const maisons = [{ nom: "Maison haut de gamme", price: 1150, favoris: true, txt: "Maison à vendre", nbbath: 3, nbsize: "250 m²", img: "/public/house.jpg" },
{ nom: "Maison abordable", price: 880, favoris: false, txt: "Maison à vendre", nbbath: 2, nbsize: "120 m²", img: "/public/house2.jpg" },
{ nom: "Maison bas de gamme", price: 562, txt: "Maison à vendre", nbbath: 1, nbsize: "90 m²", img: "/public/house3.jpg" }]

</script>