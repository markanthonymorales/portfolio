<script setup>
import { profile } from '../data/profile.js'
</script>

<template>
  <div class="bento-card bento-card--accent status-card">
    <span class="card-label">Available For</span>
    <p class="status-card__text">Remote roles &amp; consulting engagements</p>
    <div class="status-card__indicator">
      <span class="status-dot"></span>
      <span class="status-label">Open to opportunities</span>
    </div>
    <a :href="'mailto:' + profile.email" class="btn btn-accent status-card__cta">Get in Touch</a>
  </div>
</template>

<style scoped>
.status-card__text {
  font-size: var(--font-size-base);
  color: #ffffff;
  margin-bottom: 12px;
  line-height: 1.5;
}

.status-card__indicator {
  display: flex;
  align-items: center;
  gap: 8px;
  margin-bottom: 16px;
}

.status-dot {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background: #4ade80;
  animation: pulse-dot 2s ease-in-out infinite;
}

@keyframes pulse-dot {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.4; }
}

.status-label {
  font-size: var(--font-size-xs);
  color: rgba(255, 255, 255, 0.7);
}

.status-card__cta {
  width: 100%;
  text-align: center;
}
</style>
