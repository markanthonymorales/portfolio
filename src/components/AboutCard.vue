<script setup>
import { profile } from '../data/profile.js'
</script>

<template>
  <div class="bento-card about-card">
    <span class="card-label">About</span>
    <p class="about-card__text">{{ profile.summary }}</p>
    <div class="about-card__extras">
      <div class="about-card__detail">
        <span class="about-card__detail-label">Education</span>
        <span class="about-card__detail-value">{{ profile.education.degree }}</span>
        <span class="about-card__detail-sub">{{ profile.education.school }} ({{ profile.education.year }})</span>
      </div>
      <div class="about-card__detail">
        <span class="about-card__detail-label">Languages</span>
        <span class="about-card__detail-value">{{ profile.languages.join(' / ') }}</span>
      </div>
      <div class="about-card__detail">
        <span class="about-card__detail-label">Volunteer</span>
        <span class="about-card__detail-value">{{ profile.volunteer }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-card__text {
  font-size: var(--font-size-sm);
  color: var(--color-text);
  line-height: 1.7;
  margin-bottom: 20px;
}

.about-card__extras {
  display: flex;
  gap: 24px;
  flex-wrap: wrap;
}

.about-card__detail {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.about-card__detail-label {
  font-size: var(--font-size-xs);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--color-text-muted);
}

.about-card__detail-value {
  font-size: var(--font-size-sm);
  font-weight: 500;
  color: var(--color-text);
}

.about-card__detail-sub {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
}
</style>
