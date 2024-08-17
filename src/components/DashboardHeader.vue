<template>
  <header class="bg-red-400 text-black p-4 flex items-center justify-between">
    <div class="flex items-center space-x-4">
      <img src="@/assets/images/logo.png" alt="Logo" class="logo" />
      <h1 class="title text-xl font-semibold">Rock Repair & IT solutions</h1>
    </div>

    <nav class="flex space-x-4">
      <a href="tel:13072122648" class="text-xl font-bold text-black title">307-212-2648</a>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'DashboardHeader'
}
</script>

<style scoped>
@font-face {
  font-family: 'Orbitron';
  src: url('@/assets/fonts/Orbitron.ttf') format('truetype');
}

.title {
  font-family: 'Orbitron', sans-serif;
  /* You can further style the font to make it more "robotic" */
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #1f2937; /* Darker text color */
}
.logo {
  height: 7vh;
}
</style>
