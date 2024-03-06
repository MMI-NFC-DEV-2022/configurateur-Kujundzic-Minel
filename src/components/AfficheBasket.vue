<script setup lang="ts">
// Importe un type personnalisé pour s'assurer que les props passées au composant respectent une certaine structure.
import { supabase } from '@/supabase';

let { data: chaussureSvg } = await supabase
  .from('chaussureSvg')
  .select('*')
  console.log(chaussureSvg)
</script>

<template>
<p>test</p>
</template>
