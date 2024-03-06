<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import {Suspense} from 'vue'
import Personnalisation from 'src/pages/Personnalisation.vue'
import Index from 'src/pages/index.vue'
</script>

<template>
  <header class="flex space-x-72 justify-center bg-gray-500 p-3 text-white font-3xl">
    <RouterLink to="/personnalisation">Personnalisation</RouterLink>
    <RouterLink to="/">Index</RouterLink>
  </header>

  <Suspense>
    <RouterView />
  </Suspense>
</template>
