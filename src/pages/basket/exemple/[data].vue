<script setup lang="ts">
import formEditBasket from "@/components/formEditBasket.vue";
import {useRoute} from "vue-router/auto"
const route=useRoute("/basket/exemple/[data]")
</script>
<template>
  <formEditBasket :data="JSON.parse(route.params.data)" />
</template>