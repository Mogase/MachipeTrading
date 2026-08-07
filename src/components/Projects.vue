<template>
  <section class="projects" id="projects">
    <div class="container">
      <h2 class="section-title text-center">Featured <span>Projects</span></h2>
      <p class="section-sub text-center mx-auto">
        Proven track record of delivering excellence.
      </p>
      <div class="projects-grid">
        <div class="project-card" v-for="p in projects" :key="p.title">
          <div class="project-image">
            <img :src="p.img" :alt="p.title" />
          </div>
          <span class="tag">{{ p.tag }}</span>
          <h4>{{ p.title }}</h4>
          <div class="client">{{ p.client }}</div>
          <div class="desc">{{ p.desc }}</div>
        </div>
      </div>

      <div class="fleet-section">
        <div class="fleet-card">
          <div class="fleet-image">
            <img src="https://coresg-normal.trae.ai/api/ide/v1/text_to_image?prompt=8%20ton%20commercial%20truck%20with%20detachable%20water%20tanker%2C%20yellow%20construction%20vehicle%2C%20professional%20photo%2C%20industrial%20setting%2C%20high%20quality&image_size=landscape_16_9" alt="8-Ton Truck Water Tanker" />
          </div>
          <div class="fleet-content">
            <span class="fleet-badge">Owned Fleet</span>
            <h3>8-Ton Truck &ndash; General Transport &amp; Water Tanker</h3>
            <p class="fleet-lead">
              A versatile in-house 8-ton truck offering dual-purpose capability for reliable logistics and bulk water delivery.
            </p>
            <ul class="fleet-features">
              <li>
                <span class="ff-icon">🚚</span>
                <div>
                  <strong>General Goods Transport</strong>
                  <small>Building materials, construction supplies, equipment, and general cargo — locally and regionally.</small>
                </div>
              </li>
              <li>
                <span class="ff-icon">💧</span>
                <div>
                  <strong>Water Tanker Service</strong>
                  <small>Reliable bulk water delivery for construction sites, events, municipal projects, and emergency supply.</small>
                </div>
              </li>
              <li>
                <span class="ff-icon">✅</span>
                <div>
                  <strong>Available for Contract Hire</strong>
                  <small>Short-term or long-term hire — flexible scheduling to match your project timeline.</small>
                </div>
              </li>
            </ul>
            <a href="#contact" class="btn-primary">Enquire About Hiring</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import housingImg from '../assets/image.png'
import municipalImg from '../assets/municipal.png'
import plasterImg from '../assets/plaster.png'

export default {
  data() {
    return {
      projects: [
        {
          tag: 'Housing',
          title: 'Low-Cost Housing Plastering',
          client: 'Client: W F Kroon',
          desc: 'Successfully delivered extensive plastering works for large-scale low-cost housing developments.',
          img: housingImg
        },
        {
          tag: 'Commercial',
          title: 'Commercial Plastering',
          client: 'Client: Lekrom Pty (Ltd) – Elandspoort',
          desc: 'Executed high-standard plastering finishes for a major commercial project, meeting rigorous specifications.',
          img: plasterImg
        },
        {
          tag: 'Municipal',
          title: 'Municipal Housing Project',
          client: 'Client: Shomang Construction – City of Tshwane',
          desc: 'Played a key role in the city\'s low-cost housing initiative, delivering quality plastering to hundreds of units.',
          img: municipalImg
        }
      ]
    }
  }
}
</script>

<style scoped>
.fleet-section {
  margin-top: 56px;
}
.fleet-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  background: linear-gradient(135deg, #1b4332 0%, #2d6a4f 100%);
  border-radius: 24px;
  overflow: hidden;
  box-shadow: 0 20px 60px rgba(27, 67, 50, 0.2);
}
.fleet-image {
  width: 100%;
  height: 100%;
  min-height: 380px;
  background: #0b2a1c;
}
.fleet-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
.fleet-content {
  padding: 44px 40px;
  color: #fff;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.fleet-badge {
  display: inline-block;
  background: rgba(212, 160, 22, 0.18);
  color: #d4a016;
  padding: 6px 16px;
  border-radius: 40px;
  font-size: 0.78rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.8px;
  margin-bottom: 16px;
  border: 1px solid rgba(212, 160, 22, 0.28);
  align-self: flex-start;
}
.fleet-content h3 {
  font-size: 1.9rem;
  font-weight: 800;
  line-height: 1.2;
  margin-bottom: 14px;
  color: #fff;
  letter-spacing: -0.3px;
}
.fleet-lead {
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.78);
  margin-bottom: 24px;
  line-height: 1.65;
}
.fleet-features {
  list-style: none;
  padding: 0;
  margin: 0 0 28px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.fleet-features li {
  display: flex;
  gap: 14px;
  align-items: flex-start;
  padding: 12px 14px;
  background: rgba(255, 255, 255, 0.04);
  border-radius: 12px;
  border: 1px solid rgba(255, 255, 255, 0.06);
}
.ff-icon {
  font-size: 1.4rem;
  line-height: 1;
  flex-shrink: 0;
  margin-top: 2px;
}
.fleet-features strong {
  display: block;
  color: #fff;
  font-size: 0.98rem;
  font-weight: 600;
  margin-bottom: 2px;
}
.fleet-features small {
  display: block;
  color: rgba(255, 255, 255, 0.68);
  font-size: 0.85rem;
  line-height: 1.5;
}
.fleet-content .btn-primary {
  align-self: flex-start;
  background: #d4a016;
  color: #1b4332;
}
.fleet-content .btn-primary:hover {
  background: #fff;
  color: #1b4332;
}
@media (max-width: 900px) {
  .fleet-card {
    grid-template-columns: 1fr;
  }
  .fleet-image {
    min-height: 260px;
  }
  .fleet-content {
    padding: 32px 24px;
  }
  .fleet-content h3 {
    font-size: 1.5rem;
  }
}
</style>
