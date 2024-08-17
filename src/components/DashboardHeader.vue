<template>
  <header class="bg-red-400 text-black p-4 flex flex-col md:flex-row items-center justify-between">
    <div class="flex items-center space-x-4 mb-2 md:mb-0">
      <img src="@/assets/images/logo.png" alt="Logo" class="logo" />
      <h1 class="title text-xl font-semibold">Rock Repair & IT solutions</h1>
    </div>

    <nav class="flex flex-col md:flex-row space-y-2 md:space-y-0 md:space-x-4 items-center">
      <a href="tel:13072122648" class="text-xl font-bold text-black title">307-212-2648</a>
      <a><span style="font-size: 2rem">•</span></a>
      <a href="mailto:rockrepair@protonmail.com" class="text-xl font-bold text-black title"
        >rockrepair@protonmail.com</a
      >
    </nav>
  </header>
</template>

<script>
export default {
  name: 'DashboardHeader'
}
</script>

<style>
@font-face {
  font-family: 'Orbitron';
  src: url('@/assets/fonts/Orbitron.ttf') format('truetype');
}

.title {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #1f2937; /* Darker text color */
}

.logo {
  height: 7vh;
}
</style>
