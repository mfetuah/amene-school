<template>
  <section class="welcome section">
    <div class="container">
      <div class="welcome__grid">
        <div class="welcome__text">
          <span class="section-label">Welcome to Amene International School</span>
          <h2 class="welcome__title">A Caring & Nurturing Environment for Every Child</h2>
          <p class="welcome__body">
            We at Amene International School create a caring and nurturing environment by fostering
            interactive, supportive partnerships with the home and school. We enrich our school
            children's lives by offering opportunities to serve the community while instilling in them
            the virtue of life of integrity.
          </p>
          <p class="welcome__body">
            They are trained to be committed to our community with accountability and discipline —
            producing life-long learners with a comprehensive academic foundation at various ability levels.
          </p>
          <NuxtLink to="/about" class="btn btn-outline" style="margin-top: 0.5rem;">
            Read Our Full Story
          </NuxtLink>
        </div>

        <div class="welcome__stats">
          <div v-for="stat in stats" :key="stat.label" class="welcome__stat">
            <span class="welcome__stat-number">{{ stat.number }}</span>
            <span class="welcome__stat-label">{{ stat.label }}</span>
          </div>
          <div class="welcome__image-wrap">
            <img src="/images/amene-tranparent-logo.png" alt="Amene International School" class="welcome__logo" />
            <p class="welcome__motto">"Transforming minds to be Tomorrow's Leaders"</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const stats = [
  { number: '3', label: 'Academic Levels' },
  { number: '6am', label: 'School Opens Daily' },
  { number: '3', label: 'School Buses' },
  { number: '100%', label: 'Commitment to Excellence' },
]
</script>

<style scoped>
.welcome {
  background: var(--color-white);
}

.welcome__grid {
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: var(--space-16);
  align-items: center;
}

.welcome__title {
  margin: var(--space-3) 0 var(--space-5);
  font-size: clamp(1.6rem, 3.5vw, 2.4rem);
}

.welcome__body {
  margin-bottom: var(--space-4);
  font-size: 1rem;
  line-height: 1.8;
}

.welcome__stats {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-4);
}

.welcome__stat {
  background: var(--color-base);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-md);
  padding: var(--space-6);
  text-align: center;
  display: flex;
  flex-direction: column;
  gap: var(--space-2);
}

.welcome__stat-number {
  font-family: var(--font-heading);
  font-size: 2.25rem;
  color: var(--color-primary);
  line-height: 1;
}

.welcome__stat-label {
  font-size: 0.8rem;
  font-weight: 500;
  color: var(--color-muted);
}

.welcome__image-wrap {
  grid-column: 1 / -1;
  background: linear-gradient(135deg, var(--color-primary) 0%, #a8401e 100%);
  border-radius: var(--radius-md);
  padding: var(--space-6);
  text-align: center;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-3);
}

.welcome__logo {
  width: 56px;
  height: 56px;
  object-fit: contain;
  filter: brightness(0) invert(1) drop-shadow(0 1px 4px rgba(0,0,0,0.2));
}

.welcome__motto {
  font-family: var(--font-heading);
  font-style: italic;
  font-size: 0.95rem;
  color: rgba(255, 255, 255, 0.95);
  line-height: 1.5;
  margin: 0;
  font-weight: 600;
}

@media (max-width: 900px) {
  .welcome__grid { grid-template-columns: 1fr; }
}
</style>
