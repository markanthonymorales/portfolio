<script setup>
import { onMounted } from 'vue'
import ThemeToggle from './components/ThemeToggle.vue'
import IdentityCard from './components/IdentityCard.vue'
import StatusCard from './components/StatusCard.vue'
import StatsCard from './components/StatsCard.vue'
import AboutCard from './components/AboutCard.vue'
import SkillsCard from './components/SkillsCard.vue'
import ExperienceCard from './components/ExperienceCard.vue'
import ProjectCard from './components/ProjectCard.vue'
import CertificationsCard from './components/CertificationsCard.vue'
import AwardsCard from './components/AwardsCard.vue'
import TestimonialsCard from './components/TestimonialsCard.vue'
import DownloadCard from './components/DownloadCard.vue'
import ContactCard from './components/ContactCard.vue'

onMounted(() => {
  const cards = document.querySelectorAll('.bento-card')
  cards.forEach((card, i) => {
    setTimeout(() => {
      card.classList.add('visible')
    }, i * 60)
  })
})
</script>

<template>
  <div class="app-wrapper">
    <ThemeToggle />
    <main class="bento-grid">
      <IdentityCard class="card-span-2" />
      <StatusCard class="card-span-1" />
      <StatsCard class="card-span-1" />
      <AboutCard class="card-span-2" />
      <SkillsCard class="card-span-2" />
      <ExperienceCard class="card-span-4" />
      <ProjectCard class="card-span-2" />
      <CertificationsCard class="card-span-1" />
      <AwardsCard class="card-span-1" />
      <TestimonialsCard class="card-span-2" />
      <DownloadCard class="card-span-1" />
      <ContactCard class="card-span-1" />
    </main>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--font-family);
  background: var(--color-bg);
  color: var(--color-text);
  line-height: 1.6;
  transition: background var(--transition-base), color var(--transition-base);
}

.app-wrapper {
  min-height: 100vh;
  position: relative;
}
</style>
