<template>
  <header
    class="bg-gradient-to-r from-blue-400 to-blue-600 text-white p-4 flex flex-col md:flex-row items-center justify-between shadow-lg"
  >
    <div class="flex items-center space-x-4 mb-2 md:mb-0">
      <img src="@/assets/images/logo.png" alt="Logo" class="logo" />
      <h3 class="title text-lg font-bold tracking-wide">Rock Repair & IT Solutions</h3>
    </div>

    <nav class="flex flex-col md:flex-row space-y-2 md:space-y-0 md:space-x-4 items-center">
      <a
        href="tel:13072122648"
        class="text-lg font-semibold hover:text-yellow-300 transition-colors"
        >307-212-2648</a
      >
      <span class="hidden md:block" style="font-size: 2rem">•</span>
      <a
        href="mailto:rockrepair@protonmail.com"
        class="text-lg font-semibold hover:text-yellow-300 transition-colors"
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

<style scoped>
@font-face {
  font-family: 'Orbitron';
  src: url('@/assets/fonts/Orbitron.ttf') format('truetype');
}

.title {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 2px;
  text-transform: uppercase;
}

.logo {
  height: 6vh;
  object-fit: contain;
}

@media (max-width: 768px) {
  .logo {
    height: 5vh;
    max-height: 40px;
  }

  .title {
    font-size: 1.5rem;
  }

  header {
    padding: 2rem 1.5rem;
  }
}
</style>
