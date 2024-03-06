<script setup lang="ts">
import { ref } from 'vue'
import type { ChaussureSvg } from '@/types'
import { colors } from '@/types'
import { materiaux } from '@/types'
import SvgProfil from '@/components/SvgProfil.vue'
import SvgDessus from '@/components/SvgDessus.vue'

const props = defineProps<{
  data?: ChaussureSvg
  id?: string
}>()

const basket = ref<ChaussureSvg>(props.data ?? {})
</script>

<template>
  <h1 class="3xl font-bold">AFFICHAGE AVEC SELECT</h1>

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

    <FormKit type="form" v-model="basket">
      <FormKit
        name="semelle"
        label="semelle"
        value="#ffffff"
        type="select"
        :options="colors"
      ></FormKit>
      <FormKit
        name="empeigne"
        label="empeigne"
        value="#ffffff"
        type="select"
        :options="colors"
      ></FormKit>
      <FormKit
        name="pointe"
        label="pointe"
        value="#ffffff"
        type="select"
        :options="colors"
      ></FormKit>
      <FormKit
        name="oeillet"
        label="oeillet"
        value="#ffffff"
        type="select"
        :options="colors"
      ></FormKit>
      <FormKit name="bande" label="bande" value="#ffffff" type="select" :options="colors"></FormKit>
      <FormKit
        name="languette"
        label="languette"
        value="#ffffff"
        type="select"
        :options="colors"
      ></FormKit>
      <FormKit name="lacet" label="lacet" value="#ffffff" type="select" :options="colors"></FormKit>
      <FormKit
        name="trimestre"
        label="trimestre"
        value="#ffffff"
        type="select"
        :options="colors"
      ></FormKit>
    </FormKit>
  </div>

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

    <FormKit type="form" v-model="basket">
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
          <div class="h-6 w-6 rounded-full border-2 peer-checked:border-red-600" :style="{ backgroundImage: 
          `url(${context.option.value})` }" />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="semelle"
        label="semelle"
        value="#ffffff"
        type="radio"
        :options="colors"
        :sections-schema="{
          inner: { $el: null },
          decorator: { $el: null }
        }"
        input-class="peer sr-only"
        options-class="flex gap-1"
      >
        <template #label="context">
          <div class="h-6 w-6 rounded-full border-2 peer-checked:border-red-600" :style="{ backgroundColor: context.option.value }" />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="empeigne"
        label="empeigne"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="pointe"
        label="pointe"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="oeillet"
        label="oeillet"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="bande"
        label="bande"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="languette"
        label="languette"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="lacet"
        label="lacet"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
      <FormKit
        name="trimestre"
        label="trimestre"
        value="#ffffff"
        type="radio"
        :options="colors"
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
            :style="{ backgroundColor: context.option.value }"
          />
          <span class="sr-only">{{ context.option.label }} </span>
        </template>
      </FormKit>
    </FormKit>
  </div>

</template>
