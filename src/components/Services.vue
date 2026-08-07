<template>
  <section class="services" id="services">
    <div class="container">
      <h2 class="section-title text-center">Our <span>Services</span></h2>
      <p class="section-sub text-center mx-auto">
        Comprehensive construction solutions delivered with precision.
      </p>
      <div class="services-grid">
        <div class="service-card" v-for="s in services" :key="s.title">
          <span class="icon">{{ s.icon }}</span>
          <h4>{{ s.title }}</h4>
          <p>{{ s.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      services: [
        { icon: '', title: 'General Building Works', desc: 'Full-scope construction and building services.' },
        { icon: '', title: 'Ceiling Installation', desc: 'Suspended, Bulkhead, and Custom ceiling systems.' },
        { icon: '', title: 'Painting', desc: 'Interior &amp; Exterior – premium finishes for all surfaces.' },
        { icon: '', title: 'Plastering', desc: 'Fine Finishes, Screeding, and Structural Repairs.' },
        { icon: '', title: 'Tiling', desc: 'Floor, Wall, and Specialized Surface installations.' },
      ]
    }
  }
}
</script>