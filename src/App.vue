<script setup>
import { RouterView } from 'vue-router'
import DashboardHeader from './components/DashboardHeader.vue'
import FixedFooter from './components/FixedFooter.vue'
</script>

<template>
  <DashboardHeader />
  <main class="p-4 overflow-x-hidden bg-gray-600">
    <RouterView />
  </main>
  <FixedFooter
    class="relative sz-50 bottom-0 left-0 w-full bg-blue-500 text-white text-center p-2 shadow-md"
  />
</template>
