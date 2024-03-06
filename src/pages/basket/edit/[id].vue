<script setup lang="ts">
import formEditBasket from "../../../components/formEditBasket.vue";
defineProps<{
  id: string;
}>();
</script>
<template>
  <formEditBasket :id="id" />
</template>