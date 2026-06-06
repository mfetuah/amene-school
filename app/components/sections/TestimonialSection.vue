<template>
  <section class="testimonials">
    <div class="container">
      <div class="section-header" style="margin-bottom: var(--space-10);">
        <span class="section-label" style="color: var(--color-secondary);">Parent Testimonials</span>
        <h2 class="section-title" style="color: #fff;">What Parents Say About Us</h2>
      </div>

      <div class="testimonials__grid">
        <div
          v-for="(t, i) in testimonials"
          :key="i"
          class="testimonial-card"
          :class="{ 'testimonial-card--featured': i === 1 }"
        >
          <div class="testimonial-card__quote">"</div>
          <p class="testimonial-card__text">{{ t.text }}</p>
          <div class="testimonial-card__author">
            <div class="testimonial-card__avatar">{{ t.initials }}</div>
            <div>
              <p class="testimonial-card__name">{{ t.name }}</p>
              <p class="testimonial-card__role">{{ t.role }}</p>
            </div>
          </div>
          <div class="testimonial-card__stars">★★★★★</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const testimonials = [
  {
    initials: 'AO',
    name: 'Mrs. Akosua Owusu',
    role: 'Parent of Primary 3 Student',
    text: 'Amene International School has completely transformed my daughter. The teachers are dedicated, the environment is so warm and safe, and I can see real improvement in her confidence and academic performance every single term.',
  },
  {
    initials: 'KB',
    name: 'Mr. Kwabena Boateng',
    role: 'Parent of JHS 1 Student',
    text: 'The level of discipline and moral values taught here is exceptional. My son came home one day and explained integrity to me — that says everything about what Amene International School stands for. I couldn\'t be prouder.',
  },
  {
    initials: 'EA',
    name: 'Mrs. Efua Acheampong',
    role: 'Parent of Nursery Student',
    text: 'Enrolling my child at Amene was the best decision we made. The school bus is reliable, the teachers are kind, and my little one actually looks forward to school every morning. The nurturing environment here is truly special.',
  },
]
</script>

<style scoped>
.testimonials {
  background: var(--color-contrast);
  padding: var(--space-20) 0;
}

.testimonials__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-5);
  align-items: stretch;
}

.testimonial-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: var(--radius-lg);
  padding: var(--space-8) var(--space-6);
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
  transition: background var(--transition);
}

.testimonial-card:hover {
  background: rgba(255, 255, 255, 0.08);
}

.testimonial-card--featured {
  background: var(--color-primary);
  border-color: var(--color-primary);
  transform: scale(1.02);
}

.testimonial-card__quote {
  font-family: var(--font-heading);
  font-size: 4rem;
  line-height: 0.5;
  color: rgba(255, 255, 255, 0.25);
}

.testimonial-card--featured .testimonial-card__quote {
  color: rgba(255, 255, 255, 0.4);
}

.testimonial-card__text {
  font-family: var(--font-heading);
  font-style: italic;
  font-size: 1rem;
  line-height: 1.7;
  color: rgba(255, 255, 255, 0.88);
  flex: 1;
}

.testimonial-card__author {
  display: flex;
  align-items: center;
  gap: var(--space-3);
}

.testimonial-card__avatar {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.15);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 0.8rem;
  font-weight: 700;
  flex-shrink: 0;
}

.testimonial-card--featured .testimonial-card__avatar {
  background: rgba(255, 255, 255, 0.25);
}

.testimonial-card__name {
  font-size: 0.9rem;
  font-weight: 600;
  color: #fff;
  margin-bottom: 2px;
}

.testimonial-card__role {
  font-size: 0.75rem;
  color: rgba(255, 255, 255, 0.55);
}

.testimonial-card__stars {
  font-size: 0.85rem;
  color: #f4c430;
  letter-spacing: 2px;
}

@media (max-width: 900px) {
  .testimonials__grid { grid-template-columns: 1fr; }
  .testimonial-card--featured { transform: none; }
}
</style>
