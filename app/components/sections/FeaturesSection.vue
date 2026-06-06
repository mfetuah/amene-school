<template>
  <section class="features section">
    <div class="container">
      <div class="section-header">
        <span class="section-label">Why Choose Us</span>
        <h2 class="section-title">5 Reasons Parents Trust Amene International School</h2>
        <p class="section-subtitle">
          We don't just teach — we shape character, build confidence, and prepare every child for the future.
        </p>
      </div>

      <div class="features__grid">
        <div v-for="feature in features" :key="feature.title" class="feature-card">
          <div class="feature-card__icon-wrap">
            <span class="feature-card__icon">{{ feature.icon }}</span>
          </div>
          <h3 class="feature-card__title">{{ feature.title }}</h3>
          <p class="feature-card__desc">{{ feature.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const features = [
  {
    icon: '🎓',
    title: 'Qualified Teachers',
    desc: 'Our certified, experienced educators bring passion and expertise into every classroom, delivering quality instruction tailored to each child\'s ability level.',
  },
  {
    icon: '🛡️',
    title: 'Safe Environment',
    desc: 'A fully walled, secure campus with dedicated gate oversight ensures every child is protected and every parent is at peace throughout the school day.',
  },
  {
    icon: '📚',
    title: 'Strong Academics',
    desc: 'A rigorous, well-structured curriculum that builds critical thinking, numeracy, literacy, and practical problem-solving skills from the very first year.',
  },
  {
    icon: '🙏',
    title: 'Moral Values',
    desc: 'We instil integrity, discipline, respect, and accountability — training students to be responsible citizens committed to their community and nation.',
  },
  {
    icon: '🏫',
    title: 'Modern Facilities',
    desc: 'From our ICT lab and science lab to our library, playground, and school park — our campus is equipped to make learning dynamic and inspiring every day.',
  },
]
</script>

<style scoped>
.features {
  background: var(--color-white);
}

.features__grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: var(--space-5);
}

.feature-card {
  background: var(--color-base);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-md);
  padding: var(--space-6) var(--space-5);
  text-align: center;
  transition: box-shadow var(--transition), transform var(--transition), border-color var(--transition);
}

.feature-card:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-4px);
  border-color: var(--color-primary);
}

.feature-card__icon-wrap {
  width: 64px;
  height: 64px;
  background: rgba(216, 97, 60, 0.08);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto var(--space-4);
}

.feature-card__icon { font-size: 1.75rem; line-height: 1; }

.feature-card__title {
  font-size: 1rem;
  margin-bottom: var(--space-3);
  color: var(--color-contrast);
}

.feature-card__desc {
  font-size: 0.825rem;
  line-height: 1.7;
}

@media (max-width: 1100px) {
  .features__grid { grid-template-columns: repeat(3, 1fr); }
  .features__grid > :nth-child(4),
  .features__grid > :nth-child(5) { grid-column: auto; }
}

@media (max-width: 640px) {
  .features__grid { grid-template-columns: 1fr; }
}
</style>
