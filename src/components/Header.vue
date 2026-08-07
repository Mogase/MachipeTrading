<template>
  <header class="header">
    <div class="container">
      <div class="logo">
        <div class="logo-icon">
          <img src="../assets/logo.png" alt="Machipe Trading Logo" />
        </div>
        <div>Machipe<span>Trading</span></div>
      </div>
      <button class="hamburger" @click="menuOpen = !menuOpen">
        <span></span><span></span><span></span>
      </button>
      <nav class="nav-links" :class="{ open: menuOpen }">
        <a href="#overview" @click="menuOpen = false">Overview</a>
        <a href="#services" @click="menuOpen = false">Services</a>
        <a href="#projects" @click="menuOpen = false">Projects</a>
        <a href="#values" @click="menuOpen = false">Values</a>
        <a href="#" class="nav-cta" @click.prevent="openModal">Contact</a>
      </nav>
    </div>

    <ContactModal
      :show="showModal"
      email="mogasegase123@gmail.com"
      phone-number="0673796372"
      @close="showModal = false"
    />
  </header>
</template>

<script>
import ContactModal from './ContactModal.vue'

export default {
  components: { ContactModal },
  data() {
    return {
      menuOpen: false,
      showModal: false
    }
  },
  methods: {
    openModal() {
      this.menuOpen = false
      this.showModal = true
    }
  }
}
</script>