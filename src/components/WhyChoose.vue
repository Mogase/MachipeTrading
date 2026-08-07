<template>
  <section class="why-choose" id="why">
    <div class="container">
      <h2 class="section-title text-center">Why <span>Choose Us</span></h2>
      <p class="section-sub text-center mx-auto">
        Partner with a company that delivers on its promises.
      </p>
      <div class="why-grid">
        <div class="why-card" v-for="item in items" :key="item.title">
          <div class="number">{{ item.number }}</div>
          <h4>{{ item.title }}</h4>
          <p>{{ item.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      items: [
        { number: '20+', title: 'Years of Experience', desc: 'Wisdom of an established company since 2004.' },
        { number: '100%', title: 'HDI Ownership', desc: 'Genuinely committed to economic transformation.' },
        { number: 'Level 1', title: 'B-BBEE Status', desc: '135% Procurement Recognition – boost your scorecard.' },
        { number: '✅', title: 'Quality & Safety', desc: 'Strict quality control and workforce safety.' },
      ]
    }
  }
}
</script>