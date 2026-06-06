<template>
  <div>
    <div class="page-hero container">
      <p class="page-hero__label">Our Photos</p>
      <h1 class="page-hero__title">School Gallery</h1>
      <p class="page-hero__subtitle">A window into the vibrant life and joyful moments at Amene International School.</p>
    </div>

    <section class="gallery section">
      <div class="container">
        <div class="gallery__tabs">
          <button
            v-for="tab in tabs"
            :key="tab"
            class="gallery__tab"
            :class="{ 'gallery__tab--active': activeTab === tab }"
            @click="activeTab = tab"
          >
            {{ tab }}
          </button>
        </div>

        <div class="gallery__grid">
          <div
            v-for="(img, i) in filteredImages"
            :key="i"
            class="gallery__item"
            @click="openLightbox(i)"
          >
            <img :src="img.src" :alt="img.alt" class="gallery__img" />
            <div class="gallery__item-overlay">
              <span>🔍</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <div v-if="lightboxIndex !== null" class="lightbox" @click.self="lightboxIndex = null">
      <button class="lightbox__close" @click="lightboxIndex = null">✕</button>
      <button class="lightbox__prev" @click="prevImage">‹</button>
      <img :src="filteredImages[lightboxIndex].src" :alt="filteredImages[lightboxIndex].alt" class="lightbox__img" />
      <button class="lightbox__next" @click="nextImage">›</button>
      <p class="lightbox__caption">{{ filteredImages[lightboxIndex].alt }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'Gallery — Amene International School',
  description: 'Browse photos from Amene International School — students, activities, facilities, and more.',
})

const tabs = ['All', 'Students', 'Facilities', 'Activities']
const activeTab = ref('All')
const lightboxIndex = ref<number | null>(null)

const images = [
  { src: '/images/amene-kids.webp', alt: 'Students studying together', category: 'Students' },
  { src: '/images/amene-kids-2.jpg', alt: 'Young learners in the classroom', category: 'Students' },
  { src: '/images/amene-kids-2.webp', alt: 'Happy students', category: 'Students' },
  { src: '/images/aamene-kids-3.webp', alt: 'Students at school', category: 'Students' },
  { src: '/images/amene-kids-1-copy.jpg', alt: 'Children learning', category: 'Activities' },
  { src: '/images/amene_bus_enhanced.png', alt: 'School transportation bus', category: 'Facilities' },
  { src: '/images/amene-table.jpg', alt: 'School resources', category: 'Facilities' },
  { src: '/images/WhatsApp-Image-2026-03-04-at-8.38.50-AM.jpeg', alt: 'School event', category: 'Activities' },
  { src: '/images/WhatsApp-Image-2026-03-04-at-8.38.53-AM.jpeg', alt: 'School activity', category: 'Activities' },
  { src: '/images/WhatsApp-Image-2026-01-22-at-6.33.39-PM-1.jpeg', alt: 'School life', category: 'Activities' },
]

const filteredImages = computed(() =>
  activeTab.value === 'All' ? images : images.filter(img => img.category === activeTab.value)
)

function openLightbox(index: number) {
  lightboxIndex.value = index
}

function prevImage() {
  if (lightboxIndex.value === null) return
  lightboxIndex.value = (lightboxIndex.value - 1 + filteredImages.value.length) % filteredImages.value.length
}

function nextImage() {
  if (lightboxIndex.value === null) return
  lightboxIndex.value = (lightboxIndex.value + 1) % filteredImages.value.length
}
</script>

<style scoped>
.gallery__tabs {
  display: flex;
  gap: var(--space-2);
  margin-bottom: var(--space-8);
  flex-wrap: wrap;
}

.gallery__tab {
  padding: 0.5rem 1.25rem;
  border: 1px solid var(--color-border);
  border-radius: 99px;
  background: transparent;
  font-family: var(--font-body);
  font-size: 0.875rem;
  font-weight: 500;
  cursor: pointer;
  transition: all var(--transition);
  color: var(--color-muted);
}

.gallery__tab:hover {
  border-color: var(--color-primary);
  color: var(--color-primary);
}

.gallery__tab--active {
  background: var(--color-primary);
  border-color: var(--color-primary);
  color: #fff;
}

.gallery__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-4);
}

.gallery__item {
  position: relative;
  border-radius: var(--radius-md);
  overflow: hidden;
  cursor: pointer;
  aspect-ratio: 4/3;
}

.gallery__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.gallery__item-overlay {
  position: absolute;
  inset: 0;
  background: rgba(17, 17, 17, 0.45);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  opacity: 0;
  transition: opacity var(--transition);
}

.gallery__item:hover .gallery__img { transform: scale(1.06); }
.gallery__item:hover .gallery__item-overlay { opacity: 1; }

.lightbox {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.92);
  z-index: 500;
  display: flex;
  align-items: center;
  justify-content: center;
}

.lightbox__img {
  max-width: 90vw;
  max-height: 85vh;
  object-fit: contain;
  border-radius: var(--radius-sm);
}

.lightbox__close {
  position: absolute;
  top: var(--space-5);
  right: var(--space-5);
  background: rgba(255,255,255,0.1);
  border: none;
  color: #fff;
  font-size: 1.25rem;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
}

.lightbox__prev,
.lightbox__next {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255,255,255,0.1);
  border: none;
  color: #fff;
  font-size: 2rem;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background var(--transition);
}

.lightbox__prev { left: var(--space-5); }
.lightbox__next { right: var(--space-5); }
.lightbox__prev:hover, .lightbox__next:hover { background: rgba(255,255,255,0.2); }

.lightbox__caption {
  position: absolute;
  bottom: var(--space-6);
  left: 50%;
  transform: translateX(-50%);
  color: rgba(255,255,255,0.7);
  font-size: 0.875rem;
  text-align: center;
}

@media (max-width: 768px) {
  .gallery__grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 480px) {
  .gallery__grid { grid-template-columns: 1fr; }
}
</style>
