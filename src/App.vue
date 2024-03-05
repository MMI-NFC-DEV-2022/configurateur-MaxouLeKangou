<script setup lang="ts">
import { RouterLink, RouterView, } from 'vue-router'
import { supabase, signInWithGithub } from './supabase'

import svgProfil from './components/svgProfil.vue'

</script>

<template>
    <svgProfil />
    <RouterView/>
</template>
