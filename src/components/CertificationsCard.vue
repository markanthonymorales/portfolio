<script setup>
import { profile } from '../data/profile.js'
</script>

<template>
  <div class="bento-card certifications-card">
    <span class="card-label">Certifications</span>
    <ul class="certifications-card__list">
      <li v-for="cert in profile.certifications" :key="cert">
        <span class="certifications-card__icon">&#9670;</span>
        <span>{{ cert }}</span>
      </li>
    </ul>
  </div>
</template>

<style scoped>
.certifications-card__list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.certifications-card__list li {
  display: flex;
  align-items: flex-start;
  gap: 8px;
  font-size: var(--font-size-sm);
  line-height: 1.5;
}

.certifications-card__icon {
  color: var(--color-accent);
  font-size: 0.6rem;
  margin-top: 6px;
  flex-shrink: 0;
}
</style>
