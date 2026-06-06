<template>
  <section class="stats">
    <div class="container">
      <div class="stats__grid">
        <div v-for="stat in stats" :key="stat.label" class="stats__item">
          <span class="stats__number">{{ stat.number }}</span>
          <span class="stats__label">{{ stat.label }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const stats = [
  { number: '10+', label: 'Years of Excellence' },
  { number: '500+', label: 'Happy Students' },
  { number: '40+', label: 'Qualified Teachers' },
  { number: '4', label: 'Academic Programs' },
]
</script>

<style scoped>
.stats {
  background: var(--color-accent);
  padding: var(--space-12) 0;
}

.stats__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: var(--space-6);
  text-align: center;
}

.stats__item {
  display: flex;
  flex-direction: column;
  gap: var(--space-2);
  padding: var(--space-6) var(--space-4);
  border-right: 1px solid rgba(17, 17, 17, 0.12);
}

.stats__item:last-child {
  border-right: none;
}

.stats__number {
  font-family: var(--font-heading);
  font-size: clamp(2rem, 4vw, 3rem);
  color: var(--color-contrast);
  line-height: 1;
}

.stats__label {
  font-size: 0.85rem;
  font-weight: 500;
  color: var(--color-muted);
  letter-spacing: 0.02em;
}

@media (max-width: 640px) {
  .stats__grid { grid-template-columns: repeat(2, 1fr); }
  .stats__item:nth-child(2) { border-right: none; }
  .stats__item:nth-child(3) { border-right: 1px solid rgba(17, 17, 17, 0.12); }
}
</style>
