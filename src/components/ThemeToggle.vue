<script setup>
import { ref, onMounted } from 'vue'

const isDark = ref(false)

onMounted(() => {
  const saved = localStorage.getItem('theme')
  if (saved === 'dark') {
    isDark.value = true
    document.documentElement.setAttribute('data-theme', 'dark')
  }
})

function toggle() {
  isDark.value = !isDark.value
  const theme = isDark.value ? 'dark' : 'light'
  document.documentElement.setAttribute('data-theme', isDark.value ? 'dark' : '')
  localStorage.setItem('theme', theme)
}
</script>

<template>
  <button class="theme-toggle" @click="toggle" :aria-label="isDark ? 'Switch to light mode' : 'Switch to dark mode'">
    <span class="theme-toggle__icon">{{ isDark ? '&#9728;' : '&#9790;' }}</span>
  </button>
</template>

<style scoped>
.theme-toggle {
  position: fixed;
  top: 20px;
  right: 20px;
  z-index: 50;
  width: 40px;
  height: 40px;
  border-radius: 10px;
  border: 1px solid var(--color-border);
  background: var(--color-surface);
  color: var(--color-text);
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: var(--shadow-card);
  transition: transform var(--transition-fast), box-shadow var(--transition-fast);
}

.theme-toggle:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-card-hover);
}

.theme-toggle__icon {
  font-size: 1.2rem;
}
</style>
