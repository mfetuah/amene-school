<template>
  <section class="facilities section" style="background: var(--color-accent);">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Our Campus</span>
        <h2 class="section-title">World-Class School Facilities</h2>
        <p class="section-subtitle">
          Our campus is equipped with everything children need to learn, grow, explore, and thrive every day.
        </p>
      </div>

      <div class="facilities__grid">
        <div v-for="facility in facilities" :key="facility.name" class="facility-item">
          <div class="facility-item__icon">{{ facility.icon }}</div>
          <div class="facility-item__body">
            <h3 class="facility-item__name">{{ facility.name }}</h3>
            <p class="facility-item__desc">{{ facility.desc }}</p>
          </div>
        </div>
      </div>

      <div class="facilities__bus">
        <div class="facilities__bus-img">
          <img src="/images/amene_bus_enhanced.png" alt="Amene International School Bus" />
        </div>
        <div class="facilities__bus-text">
          <span class="section-label">Transportation</span>
          <h3>3 Dedicated School Buses</h3>
          <p>
            Our fleet of 3 school buses provides safe, reliable transportation for students across
            key routes, ensuring every child arrives on time and gets home safely.
          </p>
          <NuxtLink to="/contact" class="btn btn-primary" style="margin-top: 1rem;">
            Ask About Bus Routes
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const facilities = [
  { icon: '🏫', name: 'Modern Tiled Classrooms', desc: 'Bright, well-ventilated classrooms with modern tiling for a clean, inspiring learning environment.' },
  { icon: '📖', name: 'Library', desc: 'A well-stocked library encouraging a culture of reading, research, and independent learning.' },
  { icon: '💻', name: 'ICT Laboratory', desc: 'A fully equipped computer lab preparing students with 21st-century digital skills.' },
  { icon: '🚽', name: 'Sanitation Facilities', desc: 'State-of-the-art, hygienic sanitation facilities maintained to the highest standards of cleanliness.' },
  { icon: '🔒', name: 'Secured Compound', desc: 'Fully walled school compound with dedicated oversight at the school gate for maximum security.' },
  { icon: '⚽', name: 'Playground', desc: 'A spacious playground where students enjoy physical activity, sports, and unstructured play.' },
  { icon: '🌳', name: 'School Park', desc: 'A beautiful green school park providing a serene space for outdoor activities and relaxation.' },
  { icon: '🔬', name: 'Science Laboratory', desc: 'A hands-on science lab that brings lessons to life through practical experiments and discovery.' },
]
</script>

<style scoped>
.facilities__grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: var(--space-4);
  margin-bottom: var(--space-16);
}

.facility-item {
  background: var(--color-white);
  border-radius: var(--radius-md);
  padding: var(--space-5);
  display: flex;
  gap: var(--space-4);
  align-items: flex-start;
  border: 1px solid rgba(255,255,255,0.8);
  transition: box-shadow var(--transition), transform var(--transition);
}

.facility-item:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-2px);
}

.facility-item__icon {
  font-size: 1.75rem;
  flex-shrink: 0;
  line-height: 1;
}

.facility-item__name {
  font-family: var(--font-body);
  font-size: 0.9rem;
  font-weight: 600;
  margin-bottom: var(--space-1);
  color: var(--color-contrast);
}

.facility-item__desc {
  font-size: 0.8rem;
  line-height: 1.6;
}

.facilities__bus {
  background: var(--color-white);
  border-radius: var(--radius-lg);
  overflow: hidden;
  display: grid;
  grid-template-columns: 1fr 1fr;
  border: 1px solid var(--color-border);
}

.facilities__bus-img {
  aspect-ratio: 4/3;
  overflow: hidden;
}

.facilities__bus-img img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.facilities__bus-text {
  padding: var(--space-10) var(--space-10);
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: var(--space-4);
}

.facilities__bus-text h3 {
  font-size: clamp(1.3rem, 2.5vw, 2rem);
  margin: 0;
}

.facilities__bus-text p {
  font-size: 0.95rem;
  line-height: 1.7;
}

@media (max-width: 1100px) {
  .facilities__grid { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 768px) {
  .facilities__grid { grid-template-columns: 1fr; }
  .facilities__bus { grid-template-columns: 1fr; }
  .facilities__bus-text { padding: var(--space-6); }
}
</style>
