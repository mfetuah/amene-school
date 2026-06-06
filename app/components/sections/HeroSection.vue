<template>
  <section class="hero">
    <div class="hero__bg">
      <img src="/images/amene-kids-2.jpg" alt="" aria-hidden="true" class="hero__img" />
      <div class="hero__overlay" />
    </div>

    <div class="hero__content container">
      <div class="hero__logo-wrap">
        <img src="/images/amene-tranparent-logo.png" alt="Amene International School" class="hero__logo" />
      </div>

      <p class="hero__school-name">AMENE International School</p>
      <h1 class="hero__title">Transforming Minds to be<br><em>Tomorrow's Leaders</em></h1>
      <p class="hero__subtitle">
        Producing life-long learners by offering a comprehensive academic foundation
        for school children at various ability levels — from Nursery to Junior High School.
      </p>

      <div class="hero__actions">
        <NuxtLink to="/admissions" class="btn btn-primary">Apply Now</NuxtLink>
        <NuxtLink to="/contact" class="btn btn-outline-white">Learn More</NuxtLink>
      </div>

      <div class="hero__contact-strip">
        <a href="tel:+233551569990" class="hero__contact-item">
          <span>📞</span> 055 156 9990
        </a>
        <span class="hero__contact-divider">|</span>
        <a href="tel:+233599449080" class="hero__contact-item">
          <span>📞</span> 059 944 9080
        </a>
        <span class="hero__contact-divider">|</span>
        <a href="mailto:ameneedu@gmail.com" class="hero__contact-item">
          <span>✉️</span> ameneedu@gmail.com
        </a>
      </div>
    </div>

    <div class="hero__scroll">
      <div class="hero__scroll-line" />
    </div>
  </section>
</template>

<style scoped>
.hero {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: center;
  color: #fff;
  overflow: hidden;
}

.hero__bg {
  position: absolute;
  inset: 0;
  z-index: 0;
}

.hero__img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center 30%;
}

.hero__overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    150deg,
    rgba(15, 37, 64, 0.85) 0%,
    rgba(15, 37, 64, 0.5) 60%,
    rgba(216, 97, 60, 0.55) 100%
  );
}

.hero__content {
  position: relative;
  z-index: 1;
  padding-top: var(--space-24);
  padding-bottom: var(--space-20);
  text-align: center;
}

.hero__logo-wrap { margin-bottom: var(--space-5); }

.hero__logo {
  width: 80px;
  height: 80px;
  object-fit: contain;
  margin: 0 auto;
  filter: drop-shadow(0 2px 8px rgba(0,0,0,0.4));
}

.hero__school-name {
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.2em;
  text-transform: uppercase;
  color: var(--color-secondary);
  margin-bottom: var(--space-4);
}

.hero__title {
  color: #fff;
  margin-bottom: var(--space-6);
  text-shadow: 0 2px 16px rgba(0, 0, 0, 0.4);
  font-size: clamp(2.2rem, 5.5vw, 4rem);
}

.hero__title em {
  font-style: italic;
  color: var(--color-tertiary);
}

.hero__subtitle {
  color: rgba(255, 255, 255, 0.85);
  font-size: clamp(1rem, 2vw, 1.2rem);
  max-width: 600px;
  margin: 0 auto var(--space-10);
  line-height: 1.75;
}

.hero__actions {
  display: flex;
  gap: var(--space-4);
  justify-content: center;
  flex-wrap: wrap;
  margin-bottom: var(--space-10);
}

.hero__phone-icon { margin-right: var(--space-1); }

.hero__contact-strip {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: var(--space-5);
  flex-wrap: wrap;
  padding: var(--space-4) var(--space-8);
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 100px;
  backdrop-filter: blur(8px);
  max-width: 660px;
  margin: 0 auto;
}

.hero__contact-item {
  display: flex;
  align-items: center;
  gap: var(--space-2);
  font-size: 0.85rem;
  color: rgba(255, 255, 255, 0.85);
  transition: color var(--transition);
}

.hero__contact-item:hover { color: #fff; }

.hero__contact-divider {
  color: rgba(255, 255, 255, 0.25);
}

.hero__scroll {
  position: absolute;
  bottom: var(--space-8);
  left: 50%;
  transform: translateX(-50%);
  z-index: 1;
}

.hero__scroll-line {
  width: 1px;
  height: 48px;
  background: linear-gradient(to bottom, rgba(255,255,255,0.5), transparent);
  animation: scrollPulse 2s ease-in-out infinite;
}

@keyframes scrollPulse {
  0%, 100% { opacity: 0.4; transform: scaleY(0.8); }
  50% { opacity: 1; transform: scaleY(1); }
}

@media (max-width: 640px) {
  .hero__contact-strip { flex-direction: column; gap: var(--space-2); }
  .hero__contact-divider { display: none; }
  .hero__scroll { display: none; }
}
</style>
