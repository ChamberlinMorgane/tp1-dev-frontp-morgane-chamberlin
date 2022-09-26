<template>
    <div class="p-2">
        <h1 class="text-2xl">Page Liste</h1>
        <div v-for="maisons in Maison" :key="maisons.nom">
            <card class="w-1/2" v-bind="maisons" />
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref } from "@vue/reactivity";
import card from "../components/card.vue";
import { supabase } from "../supabase";

console.log("supabase :", supabase); // pour vérifier et "garder" supabase dans le code

const maisons = [supabase]

const { data: Maison, error } = await supabase
    .from('Maison')
    .select('*')


console.log("Maison", Maison)

const user = ref(supabase.auth.user());

supabase.auth.onAuthStateChange(() => {
    user.value = supabase.auth.user()
})


//globalThis.supabase = supabase//
</script>