<script setup>
import { profile } from '../data/profile.js'
</script>

<template>
  <div class="bento-card awards-card">
    <span class="card-label">Awards</span>
    <div class="awards-card__list">
      <div v-for="award in profile.awards" :key="award.title" class="awards-card__item">
        <span class="awards-card__icon">&#9733;</span>
        <div>
          <span class="awards-card__title">{{ award.title }}</span>
          <span class="awards-card__event">{{ award.event }}, {{ award.year }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.awards-card__list {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.awards-card__item {
  display: flex;
  align-items: flex-start;
  gap: 10px;
}

.awards-card__icon {
  color: var(--color-accent);
  font-size: 1.1rem;
  flex-shrink: 0;
  margin-top: 1px;
}

.awards-card__title {
  display: block;
  font-size: var(--font-size-sm);
  font-weight: 600;
  color: var(--color-text);
}

.awards-card__event {
  display: block;
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
}
</style>
