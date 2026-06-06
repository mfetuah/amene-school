<template>
  <section class="about section">
    <div class="container">
      <div class="about__grid">
        <div class="about__image-col">
          <div class="about__img-wrap">
            <img src="/images/amene-kids.webp" alt="Students at Amene International School" class="about__img" />
          </div>
          <div class="about__img-badge">
            <span class="about__badge-number">10+</span>
            <span class="about__badge-text">Years Shaping<br>Future Leaders</span>
          </div>
        </div>

        <div class="about__text-col">
          <span class="section-label">About Our School</span>
          <h2 class="about__title">A Place Where Every Child Thrives</h2>
          <p class="about__intro">
            Amene International School was founded with a clear mission: to provide world-class education
            to children in Ghana within a nurturing, inclusive, and faith-centred community.
          </p>
          <p class="about__body">
            From Nursery through Junior High School, our dedicated team of educators works tirelessly to
            identify and develop the unique talents in every child. We combine a rigorous academic curriculum
            with meaningful extracurricular activities, ensuring our students are well-prepared for the future.
          </p>

          <ul class="about__values">
            <li v-for="value in values" :key="value">
              <span class="about__check">✓</span>
              {{ value }}
            </li>
          </ul>

          <NuxtLink to="/about" class="btn btn-outline">Learn Our Story</NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const values = [
  'Academic excellence and critical thinking',
  'Character development and moral values',
  'Safe, inclusive learning environment',
  'Strong parent-school partnership',
]
</script>

<style scoped>
.about {
  background: var(--color-white);
}

.about__grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-16);
  align-items: center;
}

.about__image-col {
  position: relative;
}

.about__img-wrap {
  border-radius: var(--radius-lg);
  overflow: hidden;
  aspect-ratio: 4 / 5;
}

.about__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center top;
}

.about__img-badge {
  position: absolute;
  bottom: -var(--space-6);
  right: -var(--space-6);
  background: var(--color-primary);
  color: #fff;
  padding: var(--space-5) var(--space-6);
  border-radius: var(--radius-md);
  text-align: center;
  box-shadow: var(--shadow-md);
  bottom: var(--space-6);
  right: calc(-1 * var(--space-6));
}

.about__badge-number {
  display: block;
  font-family: var(--font-heading);
  font-size: 2.5rem;
  line-height: 1;
  margin-bottom: var(--space-2);
}

.about__badge-text {
  font-size: 0.8rem;
  font-weight: 500;
  line-height: 1.4;
  opacity: 0.9;
}

.about__title {
  font-size: clamp(1.8rem, 3.5vw, 2.5rem);
  margin: var(--space-3) 0 var(--space-5);
}

.about__intro {
  font-size: 1.05rem;
  color: var(--color-contrast);
  margin-bottom: var(--space-4);
  line-height: 1.7;
}

.about__body {
  margin-bottom: var(--space-6);
}

.about__values {
  display: flex;
  flex-direction: column;
  gap: var(--space-3);
  margin-bottom: var(--space-8);
}

.about__values li {
  display: flex;
  align-items: flex-start;
  gap: var(--space-3);
  font-size: 0.9rem;
  color: var(--color-muted);
}

.about__check {
  width: 20px;
  height: 20px;
  background: var(--color-secondary);
  color: var(--color-contrast);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.7rem;
  font-weight: 700;
  flex-shrink: 0;
  margin-top: 2px;
}

@media (max-width: 900px) {
  .about__grid {
    grid-template-columns: 1fr;
    gap: var(--space-10);
  }
  .about__img-badge {
    right: var(--space-4);
  }
}
</style>
