<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import {Suspense} from 'vue'
import Personnalisation from 'src/pages/Personnalisation.vue'
import Index from 'src/pages/index.vue'
import etape2select from 'src/pages/etape2select.vue'
import etape2radio from 'src/pages/etape2radio.vue'
import FormImage from 'src/pages/formimage.vue'
</script>

<template>
  <header class="flex space-x-48 justify-center bg-gray-500 p-3 text-white font-3xl">
    <RouterLink to="/personnalisation">Personnalisation</RouterLink>
    <RouterLink to="/">Index</RouterLink>
    <RouterLink to="/etape2select">Etape2select</RouterLink>
    <RouterLink to="/etape2radio">Etape2radio</RouterLink>
    <RouterLink to="/formimage">FormImage</RouterLink>
  </header>

  <Suspense>
    <RouterView />
  </Suspense>
</template>
