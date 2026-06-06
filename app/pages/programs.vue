<template>
  <div>
    <div class="page-hero container">
      <p class="page-hero__label">Academics</p>
      <h1 class="page-hero__title">Our Academic Programs</h1>
      <p class="page-hero__subtitle">Structured learning pathways designed to nurture every stage of your child's educational journey.</p>
    </div>

    <section class="programs section">
      <div class="container">
        <div class="programs__list">
          <div v-for="(prog, i) in programs" :key="prog.name" class="program-card" :class="{ 'program-card--alt': i % 2 !== 0 }">
            <div class="program-card__text">
              <span class="program-card__age">{{ prog.age }}</span>
              <h2 class="program-card__title">{{ prog.name }}</h2>
              <p class="program-card__desc">{{ prog.desc }}</p>
              <ul class="program-card__subjects">
                <li v-for="subject in prog.subjects" :key="subject">
                  <span class="program-card__dot" />{{ subject }}
                </li>
              </ul>
              <NuxtLink to="/admissions" class="btn btn-primary">Enroll in This Program</NuxtLink>
            </div>
            <div class="program-card__img-col">
              <img :src="prog.image" :alt="prog.name" class="program-card__img" />
            </div>
          </div>
        </div>
      </div>
    </section>

    <SectionsCtaSection />
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'Programs — Amene International School',
  description: 'Explore our academic programs: Nursery, Kindergarten, Primary, and Junior High School at Amene International School.',
})

const programs = [
  {
    name: 'Nursery',
    age: 'Ages 2 – 3',
    desc: 'Our Nursery program provides a warm, play-based environment where the youngest learners develop social skills, language, and a love for exploration through structured play and creative activities.',
    subjects: ['Language & Communication', 'Creative Play & Arts', 'Numeracy Foundations', 'Social Skills'],
    image: '/images/amene-kids.webp',
  },
  {
    name: 'Kindergarten',
    age: 'Ages 4 – 5',
    desc: 'In Kindergarten, children build on early foundations as they develop reading readiness, number sense, and problem-solving skills — all within a joyful, supportive classroom environment.',
    subjects: ['Literacy & Phonics', 'Mathematics', 'Environmental Studies', 'Physical Education'],
    image: '/images/amene-kids-2.webp',
  },
  {
    name: 'Primary School',
    age: 'Classes 1 – 6',
    desc: 'Our Primary program delivers a comprehensive curriculum that challenges students academically while encouraging curiosity, creativity, and character development across all subject areas.',
    subjects: ['English Language', 'Mathematics', 'Science', 'Social Studies', 'ICT', 'Religious & Moral Education'],
    image: '/images/aamene-kids-3.webp',
  },
  {
    name: 'Junior High School',
    age: 'JHS 1 – 3',
    desc: 'The Junior High School prepares students for the BECE and beyond. With rigorous academics, career guidance, and leadership opportunities, our JHS graduates are ready for the next chapter.',
    subjects: ['Core Mathematics', 'English Language', 'Integrated Science', 'Social Studies', 'ICT', 'French', 'Career Technology'],
    image: '/images/amene-kids-1-copy.jpg',
  },
]
</script>

<style scoped>
.programs__list {
  display: flex;
  flex-direction: column;
  gap: var(--space-16);
}

.program-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-12);
  align-items: center;
}

.program-card--alt {
  direction: rtl;
}

.program-card--alt > * {
  direction: ltr;
}

.program-card__age {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--color-primary);
  background: rgba(216, 97, 60, 0.1);
  padding: var(--space-1) var(--space-3);
  border-radius: 99px;
  margin-bottom: var(--space-3);
}

.program-card__title {
  margin-bottom: var(--space-4);
  font-size: clamp(1.5rem, 3vw, 2.25rem);
}

.program-card__desc {
  margin-bottom: var(--space-5);
  font-size: 0.95rem;
}

.program-card__subjects {
  display: flex;
  flex-direction: column;
  gap: var(--space-2);
  margin-bottom: var(--space-6);
}

.program-card__subjects li {
  display: flex;
  align-items: center;
  gap: var(--space-3);
  font-size: 0.875rem;
  color: var(--color-muted);
}

.program-card__dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--color-secondary);
  flex-shrink: 0;
}

.program-card__img-col {
  border-radius: var(--radius-lg);
  overflow: hidden;
  aspect-ratio: 4/3;
}

.program-card__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

@media (max-width: 768px) {
  .program-card,
  .program-card--alt {
    grid-template-columns: 1fr;
    direction: ltr;
  }
  .program-card__img-col { order: -1; }
}
</style>
