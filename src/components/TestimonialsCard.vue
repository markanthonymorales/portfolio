<script setup>
import { profile } from '../data/profile.js'
</script>

<template>
  <div class="bento-card references-card">
    <span class="card-label">References</span>
    <div class="references-card__list">
      <div v-for="ref in profile.references" :key="ref.name" class="references-card__item">
        <div class="references-card__name">{{ ref.name }}</div>
        <div class="references-card__role">{{ ref.role }}</div>
        <div class="references-card__company">{{ ref.company }}</div>
        <div class="references-card__location">{{ ref.location }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.references-card__list {
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.references-card__item {
  padding-left: 12px;
  border-left: 2px solid var(--color-accent);
}

.references-card__name {
  font-size: var(--font-size-sm);
  font-weight: 600;
  color: var(--color-text);
}

.references-card__role {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
}

.references-card__company {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
}

.references-card__location {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
  opacity: 0.7;
}
</style>
