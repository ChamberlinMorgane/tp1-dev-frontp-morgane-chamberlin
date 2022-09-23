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

import { supabase } from "../supabase";
console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code

const maison = [supabase]
const { data: maisons, error } = await supabase
    .from('Maison')
    .select('*')


console.log("Maison", maison)


//globalThis.supabase = supabase//
</script>