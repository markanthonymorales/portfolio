<script setup>
import { ref } from 'vue'
import { profile } from '../data/profile.js'

const selectedProject = ref(null)

function openModal(project) {
  selectedProject.value = project
}

function closeModal() {
  selectedProject.value = null
}
</script>

<template>
  <div class="bento-card project-card">
    <span class="card-label">Featured Projects</span>
    <div class="project-card__grid">
      <button
        v-for="project in profile.projects"
        :key="project.name"
        class="project-card__item"
        @click="openModal(project)"
      >
        <span class="project-card__name">{{ project.name }}</span>
        <span class="project-card__role">{{ project.role }}</span>
        <div class="project-card__tags">
          <span v-for="tech in project.tech.slice(0, 3)" :key="tech" class="pill">{{ tech }}</span>
        </div>
      </button>
    </div>

    <Teleport to="body">
      <Transition name="fade">
        <div v-if="selectedProject" class="modal-overlay" @click.self="closeModal">
          <div class="modal-content">
            <button class="modal-close" @click="closeModal">&times;</button>
            <h3 class="modal-title">{{ selectedProject.name }}</h3>
            <p class="modal-role">{{ selectedProject.role }}</p>
            <p class="modal-desc">{{ selectedProject.description }}</p>
            <div class="modal-tags">
              <span v-for="tech in selectedProject.tech" :key="tech" class="pill">{{ tech }}</span>
            </div>
          </div>
        </div>
      </Transition>
    </Teleport>
  </div>
</template>

<style scoped>
.project-card__grid {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.project-card__item {
  display: flex;
  flex-direction: column;
  gap: 4px;
  padding: 14px;
  border-radius: 8px;
  border: 1px solid var(--color-border);
  background: var(--color-bg);
  cursor: pointer;
  text-align: left;
  font-family: inherit;
  transition: border-color var(--transition-fast), background var(--transition-fast);
}

.project-card__item:hover {
  border-color: var(--color-accent);
  background: var(--color-surface);
}

.project-card__name {
  font-size: var(--font-size-base);
  font-weight: 600;
  color: var(--color-text);
}

.project-card__role {
  font-size: var(--font-size-xs);
  color: var(--color-text-muted);
}

.project-card__tags {
  display: flex;
  flex-wrap: wrap;
  gap: 4px;
  margin-top: 6px;
}

.modal-title {
  font-size: var(--font-size-xl);
  font-weight: 700;
  color: var(--color-text);
  margin-bottom: 4px;
}

.modal-role {
  font-size: var(--font-size-sm);
  color: var(--color-accent);
  font-weight: 600;
  margin-bottom: 16px;
}

.modal-desc {
  font-size: var(--font-size-sm);
  color: var(--color-text);
  line-height: 1.7;
  margin-bottom: 16px;
}

.modal-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 6px;
}
</style>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity var(--transition-base);
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
