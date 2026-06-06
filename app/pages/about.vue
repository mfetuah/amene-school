<template>
  <div>
    <div class="page-hero">
      <div class="container">
        <p class="page-hero__label">Our Story</p>
        <h1 class="page-hero__title">About AMENE International School</h1>
        <p class="page-hero__subtitle">
          Built on a foundation of excellence, integrity, and a passionate belief that every child deserves the very best education.
        </p>
      </div>
    </div>

    <!-- Vision & Mission -->
    <section class="about-vm section">
      <div class="container">
        <div class="about-vm__grid">
          <div class="about-vm__card about-vm__card--vision">
            <div class="about-vm__icon">🔭</div>
            <h2>Our Vision</h2>
            <p>Seeking to develop students with leadership qualities who will make a meaningful impact in their communities, their nation, and the world.</p>
          </div>
          <div class="about-vm__card about-vm__card--mission">
            <div class="about-vm__icon">🎯</div>
            <h2>Our Mission</h2>
            <p>Training students with a practical approach to problem-solving in our ever changing environment, equipping them with the academic and moral tools to thrive in the 21st century.</p>
          </div>
          <div class="about-vm__card about-vm__card--motto">
            <div class="about-vm__icon">⭐</div>
            <h2>Our Tagline</h2>
            <p class="about-vm__motto-text">"Transforming minds to be Tomorrow's Leaders"</p>
            <p>Every decision we make as a school is guided by this single purpose: to produce leaders who are ready for tomorrow.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Welcome / Story -->
    <section class="about-story section" style="background: var(--color-white);">
      <div class="container">
        <div class="about-story__grid">
          <div class="about-story__img-col">
            <img src="/images/amene-kids.webp" alt="Students at Amene International School" class="about-story__img" />
          </div>
          <div class="about-story__text">
            <span class="section-label">Who We Are</span>
            <h2 style="margin: var(--space-3) 0 var(--space-5);">A School That Truly Cares</h2>
            <p>
              We at Amene International School create a caring and nurturing environment by fostering
              interactive, supportive partnerships with the home and school. We enrich our school
              children's lives by offering opportunities to serve the community while instilling in them
              the virtue of life of integrity.
            </p>
            <p style="margin-top: var(--space-4);">
              They are trained to be committed to our community with accountability and discipline.
              We produce life-long learners by offering a comprehensive academic foundation for school
              children at various ability levels and preparing future leaders for the ever-changing
              challenges of the century.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Core Values -->
    <section class="about-values section">
      <div class="container">
        <div class="section-header">
          <span class="section-label">What We Stand For</span>
          <h2 class="section-title">Our Core Values</h2>
          <p class="section-subtitle">These five values are not just words, they are lived and practised in every classroom, every interaction, every day.</p>
        </div>
        <div class="about-values__grid">
          <div v-for="value in coreValues" :key="value.title" class="value-card">
            <div class="value-card__icon">{{ value.icon }}</div>
            <h3 class="value-card__title">{{ value.title }}</h3>
            <p class="value-card__desc">{{ value.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Leadership -->
    <section class="about-leadership section" style="background: var(--color-white);">
      <div class="container">
        <div class="section-header">
          <span class="section-label">Our Leadership</span>
          <h2 class="section-title">Leadership & Staff</h2>
          <p class="section-subtitle">
            Dedicated professionals who lead by example and are committed to the holistic development of every student.
          </p>
        </div>
        <div class="about-leadership__message">
          <div class="about-leadership__avatar">HT</div>
          <div class="about-leadership__quote">
            <h3>A Message from the Head Teacher</h3>
            <blockquote>
              "At Amene International School, we believe deeply that every child has unique gifts and
              unlimited potential. Our commitment is to create an environment where those gifts are
              discovered, celebrated, and developed - academically, morally, and socially. We do not
              just teach subjects; we shape futures. I warmly welcome you to our school community."
            </blockquote>
            <p class="about-leadership__attribution">— Head Teacher, AMENE International School</p>
          </div>
        </div>
      </div>
    </section>

    <SectionsCtaSection />
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'About Us — AMENE International School',
  description: 'Learn about Amene International School — our vision, mission, core values, and the leadership team behind our students\' success in Birim North, Ghana.',
})

const coreValues = [
  { icon: '📖', title: 'Knowledge', desc: 'We cultivate a deep love for learning and equip students with the knowledge they need to understand and navigate the world.' },
  { icon: '🤝', title: 'Integrity', desc: 'We teach honesty, transparency, and ethical behaviour as the foundation of every student\'s character and daily conduct.' },
  { icon: '⚖️', title: 'Discipline', desc: 'We instil self-discipline, consistency, and a strong work ethic habits that lead to excellence in every area of life.' },
  { icon: '🙌', title: 'Respect', desc: 'We foster a culture of mutual respect for fellow students, teachers, families, community, and all of creation.' },
  { icon: '💡', title: 'Innovation', desc: 'We encourage creative thinking and practical problem-solving, preparing students to lead and thrive in an ever-changing world.' },
]
</script>

<style scoped>
.about-vm__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--space-6);
}

.about-vm__card {
  padding: var(--space-8);
  border-radius: var(--radius-lg);
  border: 1px solid var(--color-border);
}

.about-vm__card--vision { background: rgba(177, 197, 164, 0.15); border-color: var(--color-secondary); }
.about-vm__card--mission { background: rgba(216, 97, 60, 0.06); border-color: var(--color-primary); }
.about-vm__card--motto { background: rgba(177, 197, 164, 0.25); border-color: var(--color-secondary); }
.about-vm__card--motto h2 { color: var(--color-contrast); }
.about-vm__card--motto p { color: var(--color-muted); }

.about-vm__icon { font-size: 2rem; margin-bottom: var(--space-4); }

.about-vm__card h2 {
  font-size: 1.4rem;
  margin-bottom: var(--space-4);
}

.about-vm__card p { font-size: 0.95rem; line-height: 1.75; }

.about-vm__motto-text {
  font-family: var(--font-heading);
  font-style: italic;
  font-size: 1.25rem;
  font-weight: 700;
  color: var(--color-primary) !important;
  margin-bottom: var(--space-4);
}

.about-story__grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--space-16);
  align-items: center;
}

.about-story__img {
  width: 100%;
  border-radius: var(--radius-lg);
  aspect-ratio: 4/5;
  object-fit: cover;
  object-position: center top;
}

.about-story__text { display: flex; flex-direction: column; }

.about-values__grid {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: var(--space-5);
}

.value-card {
  text-align: center;
  padding: var(--space-8) var(--space-6);
  background: var(--color-white);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  transition: box-shadow var(--transition), transform var(--transition);
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow: hidden;
  word-break: break-word;
}

.value-card:hover {
  box-shadow: var(--shadow-md);
  transform: translateY(-4px);
  border-color: var(--color-secondary);
}

.value-card__icon {
  font-size: 2.2rem;
  margin-bottom: var(--space-4);
  background: var(--color-base);
  width: 60px;
  height: 60px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
}

.value-card__title {
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: var(--space-3);
  color: var(--color-primary);
}

.value-card__desc {
  font-size: 0.82rem;
  line-height: 1.75;
  color: var(--color-muted);
  width: 100%;
}

.about-leadership__message {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: var(--space-8);
  align-items: flex-start;
  background: var(--color-base);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  padding: var(--space-10);
}

.about-leadership__avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--color-primary);
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.1rem;
  font-weight: 700;
  flex-shrink: 0;
}

.about-leadership__quote h3 { margin-bottom: var(--space-4); font-size: 1.2rem; }

.about-leadership__quote blockquote {
  font-family: var(--font-heading);
  font-style: italic;
  font-size: 1.05rem;
  line-height: 1.75;
  color: var(--color-contrast);
  border-left: 3px solid var(--color-primary);
  padding-left: var(--space-5);
  margin-bottom: var(--space-4);
}

.about-leadership__attribution {
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--color-muted);
}

@media (max-width: 1100px) {
  .about-values__grid { grid-template-columns: repeat(3, 1fr); }
  .about-vm__grid { grid-template-columns: 1fr; }
}

@media (max-width: 768px) {
  .about-story__grid { grid-template-columns: 1fr; }
  .about-values__grid { grid-template-columns: repeat(2, 1fr); }
  .about-leadership__message { grid-template-columns: 1fr; }
}

@media (max-width: 480px) {
  .about-values__grid { grid-template-columns: 1fr; }
}
</style>
