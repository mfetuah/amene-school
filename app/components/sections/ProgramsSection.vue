<template>
  <section class="programs section" style="background: var(--color-base);">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Academic Levels</span>
        <h2 class="section-title">Our Programs</h2>
        <p class="section-subtitle">
          A structured learning journey from early childhood through to Junior High — building strong foundations at every stage.
        </p>
      </div>

      <div class="programs__grid">
        <div v-for="program in programs" :key="program.name" class="program-card">
          <div class="program-card__img-wrap">
            <img :src="program.image" :alt="program.name" class="program-card__img" />
            <div class="program-card__badge">{{ program.ages }}</div>
          </div>
          <div class="program-card__body">
            <h3 class="program-card__title">{{ program.name }}</h3>
            <p class="program-card__desc">{{ program.desc }}</p>
            <NuxtLink to="/admissions" class="program-card__link">
              Enroll Now <span>→</span>
            </NuxtLink>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const programs = [
  {
    name: 'Nursery',
    ages: 'Ages 2 – 4',
    image: '/images/amene-kids.webp',
    desc: 'A play-based, nurturing start where young children develop language, social skills, and a lifelong love of learning in a warm, safe setting.',
  },
  {
    name: 'Primary School',
    ages: 'Class 1 – 6',
    image: '/images/amene-kids-2.jpg',
    desc: 'A comprehensive curriculum that builds strong academic foundations in literacy, numeracy, science, and creative arts while shaping character.',
  },
  {
    name: 'Junior High School',
    ages: 'JHS 1 – 3',
    image: '/images/aamene-kids-3.webp',
    desc: 'Rigorous preparation for the BECE and beyond. Students develop leadership qualities and practical problem-solving skills for the modern world.',
  },
]
</script>

<style scoped>
.programs__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-6);
}

.program-card {
  background: var(--color-white);
  border-radius: var(--radius-lg);
  overflow: hidden;
  border: 1px solid var(--color-border);
  transition: box-shadow var(--transition), transform var(--transition);
}

.program-card:hover {
  box-shadow: var(--shadow-lg);
  transform: translateY(-4px);
}

.program-card__img-wrap {
  position: relative;
  aspect-ratio: 4/3;
}

.program-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.program-card:hover .program-card__img {
  transform: scale(1.04);
}

.program-card__badge {
  position: absolute;
  top: var(--space-4);
  right: var(--space-4);
  background: var(--color-primary);
  color: #fff;
  font-size: 0.75rem;
  font-weight: 700;
  padding: var(--space-1) var(--space-3);
  border-radius: 99px;
}

.program-card__body {
  padding: var(--space-6);
  display: flex;
  flex-direction: column;
  gap: var(--space-3);
}

.program-card__title {
  font-size: 1.35rem;
}

.program-card__desc {
  font-size: 0.875rem;
  line-height: 1.7;
  flex: 1;
}

.program-card__link {
  display: inline-flex;
  align-items: center;
  gap: var(--space-2);
  font-size: 0.875rem;
  font-weight: 600;
  color: var(--color-primary);
  transition: gap var(--transition);
}

.program-card__link:hover {
  gap: var(--space-3);
}

@media (max-width: 900px) {
  .programs__grid { grid-template-columns: 1fr; }
}

@media (min-width: 640px) and (max-width: 900px) {
  .programs__grid { grid-template-columns: repeat(2, 1fr); }
  .programs__grid > :last-child { grid-column: 1 / -1; max-width: 420px; margin: 0 auto; }
}
</style>
