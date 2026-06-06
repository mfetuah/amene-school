<template>
  <section class="cta">
    <div class="cta__bg">
      <img src="/images/amene-kids-1-copy.jpg" alt="" aria-hidden="true" class="cta__bg-img" />
      <div class="cta__overlay" />
    </div>
    <div class="container cta__content">
      <span class="cta__badge">Admissions Open — 2026/27 Academic Year</span>
      <h2 class="cta__title">Give Your Child the Best Start in Life</h2>
      <p class="cta__subtitle">
        Limited places available. Secure your child's future at Amene International School today.
        Our admissions team is ready to guide you through every step.
      </p>
      <div class="cta__actions">
        <NuxtLink to="/admissions" class="btn btn-primary">Apply Now</NuxtLink>
        <a href="tel:+233551569990" class="btn btn-outline-white">📞 055 156 9990</a>
        <a href="mailto:ameneedu@gmail.com" class="btn btn-outline-white">✉️ ameneedu@gmail.com</a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.cta {
  position: relative;
  padding: var(--space-24) 0;
  overflow: hidden;
  color: #fff;
  text-align: center;
}

.cta__bg {
  position: absolute;
  inset: 0;
  z-index: 0;
}

.cta__bg-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.cta__overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(216, 97, 60, 0.9) 0%, rgba(17, 17, 17, 0.8) 100%);
}

.cta__content {
  position: relative;
  z-index: 1;
}

.cta__badge {
  display: inline-block;
  font-size: 0.75rem;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.85);
  border: 1px solid rgba(255, 255, 255, 0.35);
  padding: var(--space-2) var(--space-5);
  border-radius: 99px;
  margin-bottom: var(--space-6);
}

.cta__title {
  color: #fff;
  font-size: clamp(1.8rem, 4.5vw, 3rem);
  margin-bottom: var(--space-5);
}

.cta__subtitle {
  color: rgba(255, 255, 255, 0.85);
  font-size: 1.05rem;
  max-width: 560px;
  margin: 0 auto var(--space-8);
}

.cta__actions {
  display: flex;
  gap: var(--space-3);
  justify-content: center;
  flex-wrap: wrap;
}
</style>
