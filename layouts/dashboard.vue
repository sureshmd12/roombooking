<template>
  <div class="min-h-screen bg-gray-100 flex">
    <!-- Sidebar Component -->
    <Sidebar />

    <!-- Main Content -->
    <main class="flex-1 p-6">
      <NuxtPage />
    </main>
  </div>
</template>

<script setup>
import Sidebar from '@/components/Sidebar.vue';
</script>

<style scoped>
/* Optional: Add any custom styles here */
</style>
