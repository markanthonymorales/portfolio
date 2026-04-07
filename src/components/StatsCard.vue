<script setup>
import { ref, onMounted } from 'vue'
import { profile } from '../data/profile.js'

const counters = ref(profile.stats.map(s => ({ ...s, current: 0 })))

onMounted(() => {
  const duration = 1500
  const steps = 40
  const interval = duration / steps

  counters.value.forEach((stat) => {
    let step = 0
    const timer = setInterval(() => {
      step++
      stat.current = Math.round((step / steps) * stat.value)
      if (step >= steps) {
        stat.current = stat.value
        clearInterval(timer)
      }
    }, interval)
  })
})
</script>

<template>
  <div class="bento-card stats-card">
    <span class="card-label">At a Glance</span>
    <div class="stats-card__grid">
      <div v-for="stat in counters" :key="stat.label" class="stats-card__item">
        <span class="stats-card__number">{{ stat.current }}{{ stat.suffix }}</span>
        <span class="stats-card__label">{{ stat.label }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.stats-card__grid {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.stats-card__item {
  text-align: center;
}

.stats-card__number {
  display: block;
  font-size: var(--font-size-2xl);
  font-weight: 700;
  color: var(--color-accent);
  line-height: 1;
}

.stats-card__label {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
  margin-top: 2px;
}
</style>
