<script setup>
import { ref } from 'vue'
import { profile } from '../data/profile.js'

const expandedIndex = ref(null)

function toggle(index) {
  expandedIndex.value = expandedIndex.value === index ? null : index
}
</script>

<template>
  <div class="bento-card experience-card">
    <span class="card-label">Experience</span>
    <div class="experience-card__timeline">
      <div
        v-for="(job, index) in profile.experience"
        :key="index"
        class="experience-card__item"
        :class="{ 'experience-card__item--expanded': expandedIndex === index }"
      >
        <button class="experience-card__header" @click="toggle(index)">
          <div class="experience-card__dot"></div>
          <div class="experience-card__summary">
            <span class="experience-card__role">{{ job.role }}</span>
            <span class="experience-card__company">{{ job.company }}</span>
            <span class="experience-card__meta">{{ job.period }} &middot; {{ job.location }}</span>
          </div>
          <span class="experience-card__chevron">{{ expandedIndex === index ? '&#9650;' : '&#9660;' }}</span>
        </button>
        <Transition name="slide">
          <ul v-if="expandedIndex === index" class="experience-card__bullets">
            <li v-for="(bullet, bi) in job.bullets" :key="bi">{{ bullet }}</li>
          </ul>
        </Transition>
      </div>
    </div>
  </div>
</template>

<style scoped>
.experience-card__timeline {
  display: flex;
  flex-direction: column;
  gap: 0;
  position: relative;
}

.experience-card__item {
  position: relative;
  padding-left: 24px;
  border-left: 2px solid var(--color-border);
}

.experience-card__item:last-child {
  border-left-color: transparent;
}

.experience-card__dot {
  position: absolute;
  left: -7px;
  top: 16px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: var(--color-accent);
  border: 2px solid var(--color-surface);
}

.experience-card__header {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  width: 100%;
  padding: 12px 0;
  background: none;
  border: none;
  cursor: pointer;
  text-align: left;
  font-family: inherit;
  color: var(--color-text);
}

.experience-card__header:hover .experience-card__role {
  color: var(--color-accent);
}

.experience-card__summary {
  display: flex;
  flex-direction: column;
  gap: 2px;
  flex: 1;
}

.experience-card__role {
  font-size: var(--font-size-base);
  font-weight: 600;
  transition: color var(--transition-fast);
}

.experience-card__company {
  font-size: var(--font-size-sm);
  color: var(--color-text-muted);
}

.experience-card__meta {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
}

.experience-card__chevron {
  font-size: 0.7rem;
  color: var(--color-text-muted);
  margin-top: 4px;
  flex-shrink: 0;
}

.experience-card__bullets {
  list-style: none;
  padding: 0 0 16px 0;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.experience-card__bullets li {
  font-size: var(--font-size-sm);
  color: var(--color-text-muted);
  line-height: 1.6;
  padding-left: 16px;
  position: relative;
}

.experience-card__bullets li::before {
  content: '\25B8';
  position: absolute;
  left: 0;
  color: var(--color-accent);
}

.slide-enter-active {
  animation: slideDown var(--transition-base);
}

.slide-leave-active {
  animation: slideDown var(--transition-base) reverse;
}

@keyframes slideDown {
  from {
    opacity: 0;
    max-height: 0;
    transform: translateY(-8px);
  }
  to {
    opacity: 1;
    max-height: 500px;
    transform: translateY(0);
  }
}
</style>
