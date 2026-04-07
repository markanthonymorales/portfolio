<template>
  <div class="bento-card download-card">
    <span class="card-label">Resume</span>
    <div class="download-card__content">
      <p class="download-card__text">Download my full CV for a detailed look at my experience and skills.</p>
      <a href="./Mark_Anthony_Morales_CV.pdf" download class="btn btn-accent download-card__btn">
        <span class="download-card__icon">&#8681;</span>
        Download CV
      </a>
    </div>
  </div>
</template>

<style scoped>
.download-card__content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 16px;
}

.download-card__text {
  font-size: var(--font-size-sm);
  color: var(--color-text-muted);
  line-height: 1.5;
}

.download-card__btn {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  width: 100%;
  justify-content: center;
}

.download-card__icon {
  font-size: 1.1rem;
}
</style>
