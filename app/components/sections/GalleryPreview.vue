<template>
  <section class="gallery-preview section">
    <div class="container">
      <div class="section-header">
        <span class="section-label">School Life</span>
        <h2 class="section-title">Life at Amene International School</h2>
        <p class="section-subtitle">A glimpse into the vibrant, joyful learning environment our students enjoy every day.</p>
      </div>

      <div class="gallery-preview__grid">
        <div v-for="(img, i) in images" :key="i" class="gallery-preview__item" :class="`gallery-preview__item--${i + 1}`">
          <img :src="img.src" :alt="img.alt" class="gallery-preview__img" />
        </div>
      </div>

      <div class="gallery-preview__cta">
        <NuxtLink to="/gallery" class="btn btn-outline">View All Photos</NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const images = [
  { src: '/images/amene-kids.webp', alt: 'Students learning together' },
  { src: '/images/aamene-kids-3.webp', alt: 'Students in class' },
  { src: '/images/amene_bus_enhanced.png', alt: 'School transportation bus' },
  { src: '/images/amene-kids-2.webp', alt: 'School activities' },
  { src: '/images/amene-kids-1-copy.jpg', alt: 'Students at play' },
]
</script>

<style scoped>
.gallery-preview {
  background: var(--color-base);
}

.gallery-preview__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 260px 260px;
  gap: var(--space-4);
  margin-bottom: var(--space-8);
}

.gallery-preview__item {
  border-radius: var(--radius-md);
  overflow: hidden;
}

.gallery-preview__item--1 {
  grid-column: 1 / 3;
  grid-row: 1;
}

.gallery-preview__item--2 {
  grid-column: 3;
  grid-row: 1;
}

.gallery-preview__item--3 {
  grid-column: 1;
  grid-row: 2;
}

.gallery-preview__item--4 {
  grid-column: 2;
  grid-row: 2;
}

.gallery-preview__item--5 {
  grid-column: 3;
  grid-row: 2;
}

.gallery-preview__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.gallery-preview__item:hover .gallery-preview__img {
  transform: scale(1.04);
}

.gallery-preview__cta {
  text-align: center;
}

@media (max-width: 768px) {
  .gallery-preview__grid {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto;
  }
  .gallery-preview__item--1 { grid-column: 1 / -1; }
  .gallery-preview__item--2,
  .gallery-preview__item--3,
  .gallery-preview__item--4,
  .gallery-preview__item--5 { grid-column: auto; }
}

@media (max-width: 480px) {
  .gallery-preview__grid { grid-template-columns: 1fr; }
  .gallery-preview__item--1 { grid-column: auto; }
}
</style>
