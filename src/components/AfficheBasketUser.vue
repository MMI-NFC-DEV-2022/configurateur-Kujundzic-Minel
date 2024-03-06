<script setup lang="ts">
// Importe un type personnalisé pour s'assurer que les props passées au composant respectent une certaine structure.
import { supabase } from '@/supabase';
import BasketProfil from './BasketProfil.vue';
const props = defineProps<{
    max?: number;
}>()

const {
    data: { user }
} = await supabase.auth.getUser()


const { data: chaussureSvg } = await supabase
  .from('chaussureSvg')
  .select('*')
  .eq('id_user', user?.id)
  .limit(props.max ?? 100)
  console.log(chaussureSvg)
</script>

<template>
<p>Liste de toutes les baskets supabase</p>

<ul>
    <li v-for="nbasket in chaussureSvg" :key="index">
        <RouterLink
        :to="{
            name: '/basket/exemple/[data]',
            params: { data: JSON.stringify(nbasket) }
        }">
        <BasketProfil class="w-64" v-bind="nbasket"  />
        </RouterLink>
    </li>
</ul>

</template>
