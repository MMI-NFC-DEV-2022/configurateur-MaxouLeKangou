<script setup lang="ts">
import { RouterLink, RouterView, } from 'vue-router'
import { supabase, signInWithGithub } from './supabase'



</script>

<template>
    
  <Suspence>
    <RouterView />
  </Suspence>
</template>
