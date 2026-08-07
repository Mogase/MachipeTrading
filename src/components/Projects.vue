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
