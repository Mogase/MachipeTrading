<template>
  <section class="hero">
    <div class="container">
      <div class="hero-content">
        <div class="hero-badge">
          ★ <strong>100% Black-Owned</strong> · Level 1 B-BBEE
        </div>
        <h1>
          Building South Africa’s<br />
          <span>Future, One Project</span> at a Time
        </h1>
        <p>
          With 20+ years of grassroots experience, we deliver
          premium construction services with integrity,
          precision, and a commitment to transformation.
        </p>
        <div class="hero-cta">
          <button class="btn-primary" @click="showModal = true">Contact Us →</button>
          <a href="#services" class="btn-outline">Our Services</a>
        </div>
        <div class="hero-stats">
          <div class="stat">
            <span class="stat-number">20+</span>
            <span class="stat-label">Years Experience</span>
          </div>
          <div class="stat">
            <span class="stat-number">100%</span>
            <span class="stat-label">HDI Ownership</span>
          </div>
          <div class="stat">
            <span class="stat-number">135%</span>
            <span class="stat-label">Procurement Recognition</span>
          </div>
        </div>
      </div>
      <div class="hero-visual">
        <div class="hero-card">
          <div class="feature">
            <div class="feature-icon">🏗️</div>
            <div class="feature-text">
              General Building
              <small>Full-scope construction services</small>
            </div>
          </div>
          <div class="feature">
            <div class="feature-icon">🎨</div>
            <div class="feature-text">
              Premium Finishes
              <small>Plastering, painting &amp; tiling</small>
            </div>
          </div>
          <div class="feature">
            <div class="feature-icon">🏘️</div>
            <div class="feature-text">
              Low-Cost Housing
              <small>Municipal &amp; development projects</small>
            </div>
          </div>
        </div>
      </div>
    </div>

    <ContactModal
      :show="showModal"
      email="mogasegase123@gmail.com"
      phone-number="0673796372"
      @close="showModal = false"
    />
  </section>
</template>

<script>
import ContactModal from './ContactModal.vue'

export default {
  components: { ContactModal },
  data() {
    return {
      showModal: false
    }
  }
}
</script>

<style scoped>
.hero-cta {
  display: flex;
  gap: 14px;
  flex-wrap: wrap;
  margin-bottom: 36px;
}
.hero-cta .btn-primary,
.hero-cta .btn-outline {
  font-family: inherit;
  font-size: 1rem;
}
.feature-icon {
  width: 40px;
  height: 40px;
  background: rgba(212, 160, 22, 0.15);
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.2rem;
  color: #d4a016;
  flex-shrink: 0;
}
</style>
