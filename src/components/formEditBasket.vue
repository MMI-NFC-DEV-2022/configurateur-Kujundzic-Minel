<script setup lang="ts">
import { ref } from 'vue'
import AfficheBasket from '@/components/AfficheBasket.vue'
import type { ChaussureSvg } from '@/types'
import { materiaux } from '@/types'
import SvgProfil from '@/components/SvgProfil.vue'
import SvgDessus from '@/components/SvgDessus.vue'
import formKitListColors from '@/components/formKitListColors.vue'
import { supabase } from '@/supabase'
import { useRouter } from 'vue-router'
const router = useRouter()
const props = defineProps<{
  data?: ChaussureSvg;
  id?: string
}>()
const basket = ref<ChaussureSvg>(props.data ?? {})
async function upsertBasket(){
  const { data, error } = await supabase
    .from('chaussureSvg')
    .upsert(basket.value)
  if (error) {
    console.error('error', error)
  } else {
    router.push( '/' )
  }

}
</script>
<template>
  <h1 class="3xl font-bold">AFFICHAGE AVEC RADIO</h1>
  <div class="p-2">
    <ul class="flex gap-1">
      <li>
        <a href="#profil">Profil</a>
      </li>
      <li>
        <a href="#dessus">Dessus</a>
      </li>
    </ul>
    <div class="carousel w-64">
      <SvgProfil class="carousel-item w-64" v-bind="basket" id="profil"></SvgProfil>
      <SvgDessus class="carousel-item w-64" v-bind="basket" id="dessus"></SvgDessus>
    </div>

    <FormKit
      type="form"
      v-model="basket"
      @submit="upsertBasket"
      :config="{
        classes: {
          input: 'p-1 rounded border-gray-300 shadow-sm border',
          label: 'text-gray-600'
        }
      }"
    >
      <FormKit
        name="materiaux"
        label="Materiaux de la paire en global"
        value="#ffffff"
        type="radio"
        :options="materiaux"
        :sections-schema="{
          inner: { $el: null },
          decorator: { $el: null }
        }"
        input-class="peer sr-only"
        options-class="flex gap-1"
      >
        <template #label="context">
          <div
            class="h-6 w-6 rounded-full border-2 peer-checked:border-red-600"
            :style="{ backgroundImage: `url(${context.option.value})` }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <formKitListColors name="semelle" label="semelle" />
      <formKitListColors name="empeigne" label="empeigne" />
      <formKitListColors name="pointe" label="pointe" />
      <formKitListColors name="oeillet" label="oeillet" />
      <formKitListColors name="bande" label="bande" />
      <formKitListColors name="languette" label="languette" />
      <formKitListColors name="lacet" label="lacet" />
      <formKitListColors name="trimestre" label="trimestre" />
    </FormKit>
  </div>
  <AfficheBasket :chaussureSvg="basket" />
</template>
