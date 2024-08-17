<script setup>
import { RouterView } from 'vue-router'
import DashboardHeader from './components/DashboardHeader.vue'
import FixedFooter from './components/FixedFooter.vue'
</script>

<template>
  <DashboardHeader />
  <main class="p-4 mb-16">
    <RouterView />
  </main>
  <FixedFooter
    class="fixed bottom-0 left-0 w-full bg-red-500 text-white text-center p-2 shadow-md"
  />
</template>
