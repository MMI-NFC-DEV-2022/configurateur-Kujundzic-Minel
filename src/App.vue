<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="bg-gray-800 p-4" >
      <nav class="flex flex-row gap-10 justify-center font-bold font-poppins text-white">
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>

  <Suspense>
    <RouterView />
  </Suspense>
</template>
