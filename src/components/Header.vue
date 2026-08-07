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
        <a href="#overview">Overview</a>
        <a href="#services">Services</a>
        <a href="#projects">Projects</a>
        <a href="#values">Values</a>
        <a href="#contact" class="nav-cta">Contact</a>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return { menuOpen: false }
  }
}
</script>