<template>
  <nav>
    <div class=" lg:hidden flex items-center">
      <button v-on:click="menuNav = !menuNav " class=" py-6 px-3 ">
        <Bars3Icon class="h-10 w-10 text-red-600" :class="{hidden: !menuNav}" />
      </button>
    </div>

    <div class="flex " :class="{hidden: menuNav }">
      <button v-if="!menuNav" v-on:click="menuNav = !menuNav" class=" py-6 px-3 ">
        <XMarkIcon class="h-10 w-10 text-red-600" />
      </button>


      <ul class="justify-center m-auto">
        <li>
          <router-link class="text-black underline" to="/">
            lien vers
            <code class="font-mono">Homepage</code>
          </router-link>
        <li>
          <router-link class="text-black underline" to="/simple">
            <h2>Page Simple</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/liste">
            <h2>Page Liste</h2>
          </router-link>
        </li>
        </li>
        <li>
          <router-link class="text-black underline" to="/liste-fetch">
            <h2> Page Liste-fetch</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/edit/new">
            <h2> Page New</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/liste-supabase">
            <h2> Liste supabase</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/login-logout">
            <h2> Login-Logout</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/edit/id">
            <h2> page ID</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/quartier">
            <h2> page Index</h2>
          </router-link>
        </li>
      </ul>
    </div>


    <div class="hidden lg:flex bg-indigo-100">
      <ul class="flex space-x-4">
        <li>
          <router-link class="text-black underline" to="/">
            lien vers
            <code class="font-mono">Homepage</code>
          </router-link>
        <li>
          <router-link class="text-black underline" to="/simple">
            <h2>Page Simple</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/liste">
            <h2> Page Liste</h2>
          </router-link>
        </li>
        </li>
        <li>
          <router-link class="text-black underline" to="/liste-fetch">
            <h2> Page Liste-fetch</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/edit/new">
            <h2> Page New</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/liste-supabase">
            <h2> Liste supabase</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/login-logout">
            <h2>Login-Logout</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/edit/id">
            <h2> page ID</h2>
          </router-link>
        </li>
        <li>
          <router-link class="text-black underline" to="/quartier">
            <h2> page Index</h2>
          </router-link>
        </li>
      </ul>
    </div>
  </nav>
  <Suspense>
    <router-view class="m-2 border-2 p-2" />
  </Suspense>

</template>

<script setup lang="ts">
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/20/solid';
import { ref } from 'vue';
const menuNav = ref(true);
</script>
  