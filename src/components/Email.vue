<template>
  <div class="max-w-4xl mx-auto p-6 bg-white shadow-md rounded-lg">
    <!-- Contact Form -->
    <div class="w-full md:pr-6">
      <h2 class="text-3xl font-bold mb-6 text-center title">Contact Us</h2>
      <form action="https://formspree.io/f/xovalojl" method="POST" class="space-y-4">
        <div>
          <label for="name" class="block text-gray-700">Name</label>
          <input
            type="text"
            id="name"
            name="name"
            required
            class="w-full mt-1 p-2 border rounded"
          />
        </div>

        <div>
          <label for="email" class="block text-gray-700">Email</label>
          <input
            type="email"
            id="email"
            name="email"
            required
            class="w-full mt-1 p-2 border rounded"
          />
        </div>

        <div>
          <label for="service" class="block text-gray-700">Service Requested</label>
          <select id="service" name="service" required class="w-full mt-1 p-2 border rounded">
            <option value="" disabled selected>Select a service</option>
            <option value="Computer Repair">Computer Repair</option>
            <option value="Phone Repair">Phone Repair</option>
            <option value="Gaming System Repair">Gaming System Repair</option>
            <option value="Server Maintenance">Server Maintenance</option>
            <option value="Printer Repair">Printer Repair</option>
            <option value="POS System Setup">POS System Setup</option>
            <option value="Network Services">Network Services</option>
            <option value="Onsite Repair">Onsite Repair</option>
            <option value="Onsite Diagnosis">Onsite Diagnosis</option>
            <option value="Custom Software Solutions">Custom Software Solutions</option>
          </select>
        </div>

        <div>
          <label for="message" class="block text-gray-700">Message</label>
          <textarea
            id="message"
            name="message"
            rows="4"
            required
            class="w-full mt-1 p-2 border rounded"
          ></textarea>
        </div>

        <button
          type="submit"
          class="w-full bg-blue-400 text-white py-2 px-4 rounded hover:bg-blue-600"
        >
          Send Message
        </button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ContactForm',
  mounted() {
    // Trigger the fade-in effect after the component is mounted
    setTimeout(() => {
      document.querySelector('.fade-in').classList.add('opacity-100')
    }, 100) // Adjust timing if needed
  }
}
</script>

<style scoped>
.fade-in {
  opacity: 0;
  transition: opacity 1s ease-in-out;
}

.fade-in.opacity-100 {
  opacity: 1;
}
</style>
