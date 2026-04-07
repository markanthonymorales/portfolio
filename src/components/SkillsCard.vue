<script setup>
import { ref } from 'vue'
import { profile } from '../data/profile.js'

const activeCategory = ref(null)

function setActive(cat) {
  activeCategory.value = activeCategory.value === cat ? null : cat
}
</script>

<template>
  <div class="bento-card skills-card">
    <span class="card-label">Technical Skills</span>
    <div class="skills-card__groups">
      <div
        v-for="group in profile.skills"
        :key="group.category"
        class="skills-card__group"
        :class="{ 'skills-card__group--active': activeCategory === group.category, 'skills-card__group--dimmed': activeCategory && activeCategory !== group.category }"
      >
        <button class="skills-card__category" @click="setActive(group.category)">
          {{ group.category }}
        </button>
        <div class="skills-card__pills">
          <span v-for="item in group.items" :key="item" class="pill">{{ item }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.skills-card__groups {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.skills-card__group {
  transition: opacity var(--transition-fast);
}

.skills-card__group--dimmed {
  opacity: 0.35;
}

.skills-card__category {
  display: block;
  font-size: var(--font-size-xs);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.06em;
  color: var(--color-accent);
  margin-bottom: 6px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  font-family: inherit;
}

.skills-card__category:hover {
  text-decoration: underline;
}

.skills-card__pills {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}
</style>
