<template>
  <div class="p-4">
    <div class="mb-8">
      <div
        class="bg-light-blue-50 border border-black shadow-lg p-6 rounded-lg text-center transform scale-105"
      >
        <h2 class="text-2xl font-bold mb-4">Custom Software Solutions & Web App Design</h2>
        <p class="text-lg text-gray-700 mb-4">
          Tailored software development to meet your unique business needs. We offer full-stack
          development, API integration, and custom tools to optimize your workflow. Starting at
          $5,000 per project.
        </p>
        <button
          @click="openModal(customSoftwareService)"
          class="mt-4 bg-green-500 text-white py-2 px-6 rounded hover:bg-green-600"
        >
          Learn More
        </button>
      </div>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
      <div
        v-for="service in otherServices"
        :key="service.id"
        class="bg-light-blue-50 border border-black shadow-lg p-6 rounded-lg h-80 flex flex-col justify-between"
      >
        <div>
          <div class="mb-4">
            <img
              :src="service.image"
              :alt="service.title"
              class="w-full h-32 object-cover rounded"
            />
          </div>
          <h2 class="text-lg font-semibold mb-2">{{ service.title }}</h2>
          <p class="text-sm text-gray-600">{{ service.shortDescription }}</p>
        </div>
        <button
          @click="openModal(service)"
          class="mt-4 bg-red-300 text-white py-2 px-4 rounded hover:bg-red-600"
        >
          Learn More
        </button>
      </div>
    </div>
    <section class="mt-12">
      <ServiceAreaMap />
    </section>
    <section class="mt-12">
      <Email />
    </section>
  </div>

  <div
    v-if="selectedService"
    class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center"
  >
    <div class="bg-white p-6 rounded-lg max-w-lg w-full shadow-lg">
      <h2 class="text-2xl font-bold mb-4">{{ selectedService.title }}</h2>
      <p>{{ selectedService.fullDescription }}</p>
      <button
        @click="closeModal"
        class="mt-6 bg-red-500 text-white py-2 px-4 rounded hover:bg-red-600"
      >
        Close
      </button>
    </div>
  </div>
</template>

<script>
import Email from '@/components/Email.vue'
import ServiceAreaMap from '@/components/ServiceAreaMap.vue'

// Import images
import computerImage from '@/assets/images/computer.jpeg'
import phoneImage from '@/assets/images/phone.jpeg'
import gameImage from '@/assets/images/game.jpeg'
import serverImage from '@/assets/images/server.jpg'
import printerImage from '@/assets/images/printer.jpg'
import posImage from '@/assets/images/pos.jpg'
import networkImage from '@/assets/images/network.jpg'
import onsiteImage from '@/assets/images/onsite.jpg'
import diagImage from '@/assets/images/diag.jpg'
import telecomImage from '@/assets/images/telecom.png'

export default {
  data() {
    return {
      customSoftwareService: {
        id: 11,
        title: 'Custom Software Solutions & Web App Design',
        fullDescription:
          'We specialize in creating custom software tailored to your specific business requirements. Whether you need full-stack web development, mobile app development, or custom APIs, our team has the expertise to deliver high-quality, efficient solutions that drive your business forward. Our services also include web app design that prioritizes user experience and functionality. Pricing starts at $5,000 per project.'
      },
      otherServices: [
        {
          id: 7,
          title: 'Field Services',
          shortDescription: 'Onsite technical support and repair services.',
          fullDescription:
            'Our Field Services team provides expert onsite technical support, delivering solutions directly to your location. Whether you need critical system maintenance, network troubleshooting, cable runs, or urgent repairs, our skilled technicians are equipped to handle the situation efficiently on-site, minimizing your downtime. Field Services are available starting at $150 per hour.',
          image: telecomImage
        },
        {
          id: 1,
          title: 'Computer Repair',
          shortDescription: 'Fast and reliable computer repairs.',
          fullDescription:
            'We offer comprehensive computer repair services for all types of systems, including desktops, laptops, and servers. Whether it’s hardware issues, software problems, or data recovery, our team ensures your computer is up and running as quickly as possible. Pricing starts at $100 per repair.',
          image: computerImage
        },
        {
          id: 2,
          title: 'Phone Repair',
          shortDescription: 'Expert phone repair services.',
          fullDescription:
            'From screen replacements to battery issues, we handle all phone repairs with care and precision. Our technicians are skilled in repairing a wide range of smartphones, ensuring your device functions like new. Screen replacements start at $100.',
          image: phoneImage
        },
        {
          id: 3,
          title: 'Gaming System Repair',
          shortDescription: 'Get your gaming system back in action.',
          fullDescription:
            'We specialize in repairing gaming consoles, including PlayStation, Xbox, and Nintendo systems. Whether you’re facing hardware failures, software glitches, or connectivity issues, we provide the necessary repairs to get you back in the game. Pricing starts at $120 per repair.',
          image: gameImage
        },
        {
          id: 4,
          title: 'Server Maintenance',
          shortDescription: 'Ensure your servers are running smoothly.',
          fullDescription:
            'Our server maintenance services keep your servers optimized and secure. We provide regular updates, performance checks, and security enhancements to ensure your business operations are uninterrupted. Monthly maintenance plans start at $400 per server.',
          image: serverImage
        },
        {
          id: 5,
          title: 'Printer Repair',
          shortDescription: 'Efficient printer repair services.',
          fullDescription:
            'We fix all types of printers, from small desktop models to large office machines. Our services include troubleshooting, part replacements, and cleaning, ensuring your printers perform efficiently and reliably. Pricing starts at $120 per repair.',
          image: printerImage
        },
        {
          id: 6,
          title: 'POS System Setup',
          shortDescription: 'Professional POS system installation.',
          fullDescription:
            'We provide setup and support for POS systems, ensuring seamless operation for your business. Our services include installation, configuration, and ongoing maintenance to help you manage transactions smoothly and efficiently. Setup fee starts at $400 per system.',
          image: posImage
        },
        {
          id: 8,
          title: 'Network Services',
          shortDescription: 'Comprehensive network setup and maintenance.',
          fullDescription:
            'Our network services cover everything from running CAT5 and CAT6 cables to setting up office computers, TVs, and network devices. We ensure your entire network is configured for optimal performance, whether it’s for a small office or a larger corporate environment. Pricing starts at $150 per cable run and $600 for full network setup.',
          image: networkImage
        },
        {
          id: 9,
          title: 'Onsite Repair',
          shortDescription: 'On-site diagnosis and repair services.',
          fullDescription:
            'We offer on-site repair services, bringing our expertise directly to your location. Whether you have a critical system down or need urgent repairs, our technicians are equipped to handle the situation on-site, minimizing your downtime. On-site repairs start at $150 per hour.',
          image: onsiteImage
        },

        {
          id: 10,
          title: 'Onsite Diagnostic',
          shortDescription: 'On-site diagnostic and repair services.',
          fullDescription:
            'Our onsite diagnostic services ensure quick identification and resolution of technical issues. We come to your location to diagnose the problem, offering a detailed assessment and immediate repair options to get you back on track quickly. Diagnosis services start at $120, waived if repairs are conducted on-site.',
          image: diagImage
        }
      ],
      selectedService: null
    }
  },
  components: {
    ServiceAreaMap,
    Email
  },
  methods: {
    openModal(service) {
      this.selectedService = service
    },
    closeModal() {
      this.selectedService = null
    }
  }
}
</script>

<style scoped>
h2 {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 1.5px;
  text-transform: uppercase;
  color: #1f2937;
}

.bg-light-blue-50 {
  background-color: #f0f8ff;
}

.shadow-lg {
  box-shadow:
    0 10px 15px -3px rgba(0, 0, 0, 0.1),
    0 4px 6px -2px rgba(0, 0, 0, 0.05);
}

.border-black {
  border-color: #000;
}
</style>
