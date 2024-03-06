<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
import BasketProfil from "@/components/SvgProfil.vue";
import type { Basket } from "@/types";
import { supabase } from "@/supabase";
import { ref } from "vue";

const baskets = ref<Basket[]>([]);

async function fetchBaskets() {
  const { data, error } = await supabase.from('basket').select();
  if (error) {
    console.error("Erreur lors de la récupération des paniers depuis Supabase:", error.message);
    return;
  }
  baskets.value = data || [];
}

fetchBaskets();

function getDataString(index: number): string {
  return encodeURIComponent(JSON.stringify(baskets.value[index]));
}
</script>

<template>
  <section>
    <h1 class="text-2xl">Liste des Baskets de la BDD</h1>
    <div class="flex flex-wrap gap-2">
      <div v-for="(basket, index) in baskets" :key="index" class="w-64">
        <router-link :to="`/basket/exemple/${getDataString(index)}`">
          <BasketProfil class="w-64" v-bind="basket" />
        </router-link>
      </div>
    </div>
  </section>
</template>