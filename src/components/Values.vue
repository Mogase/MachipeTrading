<template>
  <section class="values" id="values">
    <div class="container">
      <h2 class="section-title text-center">Our <span>Core Values</span></h2>
      <p class="section-sub text-center mx-auto">
        The principles that guide everything we do.
      </p>
      <div class="values-grid">
        <div class="value-card" v-for="v in values" :key="v.title">
          <span class="emoji">{{ v.emoji }}</span>
          <h4>{{ v.title }}</h4>
          <p>{{ v.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      values: [
        { emoji: '🏆', title: 'Excellence', desc: 'Superior craftsmanship and quality assurance in every square meter.' },
        { emoji: '🤝', title: 'Professionalism', desc: 'Integrity, clear communication, and strict adherence to timelines.' },
        { emoji: '📐', title: 'Discipline', desc: 'Rigorous planning, efficient resource management, attention to detail.' },
        { emoji: '🔒', title: 'Reliability', desc: 'A partner you can count on — we deliver, no excuses.' },
      ]
    }
  }
}
</script>