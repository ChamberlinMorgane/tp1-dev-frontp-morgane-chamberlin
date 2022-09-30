<script setup lang="ts">
import { supabase } from '@/supabase';
import { useRouter } from "vue-router";
import { ref } from "@vue/reactivity";
import Card from "./card.vue"



const router = useRouter();
const maison = ref({
    nom: "Paris", price: 600, //favoris: false
    txt: "Maison haut de gamme", nbbath: 4, nbsize: "282 m²", img: "/house.jpg"
});

async function upsertMaison(dataForm, node) {
    const { data, error } = await supabase.from("Maison").upsert(dataForm);
    if (error) node.setErrors([error.message])
    else {
        node.setErrors([]);
        router.push({ name: "edit-id", params: { id: data[0].id } });
    }
}
</script>
<template>
    <div>
        <div class="p-2">
            <h2 class="text-2xl">Résultat (Prévisualisation)</h2>
            <Card class="w-1/2 m-auto mt-10" v-bind="maison" />
        </div>
        <div class="p-10 ">
            <FormKit @submit="upsertMaison" type="form" v-model="maison" :config="{
            classes: {
            input: 'p-1 rounded border-gray-500 shadow-sm border',
            label: 'text-gray-600',
            },
            }" :submit-attrs="{ classes: { input: 'bg-red-300 p-1 rounded hover:bg-green-400' } }">

                <FormKit name="nom" label="Lieu de la maison" />
                <FormKit name="price" label="Le prix de la maison" type="number" />
                <FormKit name="nbbath" label="Nombre de salle de bain" type="number" />
                <FormKit name="nbbed" label="Nombre de chambre" type="number" />
                <FormKit name="nbsize" label="Taille de la maison" type="number" />
                <FormKit name="txt" label="Adresse de la maison" />


                <!--
                    <FormKit name="favoris" label="mettre en favoris" type="checkbox" wrapper-class="flex" />-->
            </FormKit>
        </div>
    </div>
</template>