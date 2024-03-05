<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">
import { RouterLink } from "vue-router";
import BasketProfil from "../components/BasketProfil.vue";
import type { Basket } from "../types";

const exemples: Basket[] = [
	{
		semelle: "#FF0000",
		empeigne: "#FFFFFF",
		pointe: "#FFFFFF",
		oeillet: "#FFFFFF",
		bande: "#00FF00",
		languette: "#FFFFFF",
		lacet: "#00FF00",
		trimestre: "#FFFFFF",
	},
	{
		semelle: "#0000FF",
		empeigne: "#FFFF00",
		pointe: "#FFFF00",
		oeillet: "#FFFF00",
		bande: "#FF00FF",
		languette: "#FFFF00",
		lacet: "#FF00FF",
		trimestre: "#FFFF00",
	},
];
</script>
<template>
  <section>
    <h1 class="text-2xl">Exemples de Baskets</h1>
    <div class="flex flex-wrap gap-2">
      <div class="w-64">
        <!-- <RouterLink :to="{ name: 'basket-exemple-data', params: { data: JSON.stringify(exemple0) },}"> -->
          <BasketProfil class="w-64" v-for="basket in exemples" :key="basket.bande" v-bind="basket" />
        <!-- </RouterLink> -->
      </div>
    </div>
  </section>
</template>