<script setup lang="ts">
import { ref } from "vue"
import type { Basket } from '@/types';
import SvgProfil from '@/components/SvgProfil.vue';
import SvgDessus from '@/components/SvgDessus.vue';

const props = defineProps<{
    data?: Basket;
    id?: string;
}>();

const chaussure = ref<Basket>(props.data ?? {});
</script>

<template>
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
            <SvgProfil class="carousel-item w-64" v-bind="chaussure" id="profil"></SvgProfil>
            <SvgDessus class="carousel-item w-64" v-bind="chaussure" id="dessus"></SvgDessus>

        </div>



    </div>
</template>