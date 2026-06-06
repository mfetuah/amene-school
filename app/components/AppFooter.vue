<template>
  <footer class="footer">
    <div class="footer__top container">
      <div class="footer__brand">
        <NuxtLink to="/" class="footer__logo-wrap">
          <img src="/images/amene-tranparent-logo.png" alt="Amene International School" class="footer__logo" />
        </NuxtLink>
        <h3 class="footer__school-name">AMENE International School</h3>
        <p class="footer__tagline">
          Transforming minds to be Tomorrow's Leaders — producing life-long learners
          with integrity, discipline, and excellence.
        </p>
        <div class="footer__social">
          <a href="https://facebook.com" target="_blank" rel="noopener" class="footer__social-link" aria-label="Facebook">
            <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24"><path d="M18 2h-3a5 5 0 00-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 011-1h3z"/></svg>
          </a>
          <a href="https://instagram.com" target="_blank" rel="noopener" class="footer__social-link" aria-label="Instagram">
            <svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><circle cx="12" cy="12" r="4"/><circle cx="17.5" cy="6.5" r="1" fill="currentColor" stroke="none"/></svg>
          </a>
          <a href="https://wa.me/233551569990" target="_blank" rel="noopener" class="footer__social-link" aria-label="WhatsApp">
            <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.121 1.532 5.847L0 24l6.347-1.502A11.934 11.934 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 21.818a9.818 9.818 0 01-5.017-1.377l-.36-.214-3.727.882.939-3.625-.235-.373A9.818 9.818 0 0112 2.182c5.423 0 9.818 4.395 9.818 9.818 0 5.424-4.395 9.818-9.818 9.818z"/></svg>
          </a>
          <a href="https://linkedin.com" target="_blank" rel="noopener" class="footer__social-link" aria-label="LinkedIn">
            <svg width="18" height="18" fill="currentColor" viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
          </a>
        </div>
      </div>

      <div class="footer__col">
        <h4 class="footer__heading">Quick Links</h4>
        <ul class="footer__list">
          <li v-for="link in quickLinks" :key="link.to">
            <NuxtLink :to="link.to" class="footer__link">{{ link.label }}</NuxtLink>
          </li>
        </ul>
      </div>

      <div class="footer__col">
        <h4 class="footer__heading">Programs</h4>
        <ul class="footer__list">
          <li v-for="p in programs" :key="p">
            <NuxtLink to="/programs" class="footer__link">{{ p }}</NuxtLink>
          </li>
        </ul>
        <h4 class="footer__heading" style="margin-top: var(--space-6);">Office Hours</h4>
        <p class="footer__hours">Mon – Fri: 6:00 AM – 3:00 PM</p>
        <p class="footer__hours">Saturday: Admin only</p>
      </div>

      <div class="footer__col">
        <h4 class="footer__heading">Contact Us</h4>
        <ul class="footer__contact">
          <li>
            <span class="footer__contact-icon">📍</span>
            <span>EX-0072-4305, Birim North<br>Eastern Region, Ghana</span>
          </li>
          <li>
            <span class="footer__contact-icon">📞</span>
            <div>
              <a href="tel:+233551569990" class="footer__link footer__phone">055 156 9990</a><br>
              <a href="tel:+233599449080" class="footer__link footer__phone">059 944 9080</a>
            </div>
          </li>
          <li>
            <span class="footer__contact-icon">✉️</span>
            <a href="mailto:ameneedu@gmail.com" class="footer__link">ameneedu@gmail.com</a>
          </li>
          <li>
            <span class="footer__contact-icon">🌐</span>
            <span>amene.edu.gh</span>
          </li>
        </ul>
      </div>
    </div>

    <div class="footer__bottom">
      <div class="container footer__bottom-inner">
        <p>&copy; {{ year }} AMENE International School. All rights reserved.</p>
        <p>EX-0072-4305 Birim North, Eastern Region, Ghana</p>
      </div>
    </div>
  </footer>
</template>

<script setup lang="ts">
const year = new Date().getFullYear()

const quickLinks = [
  { label: 'Home', to: '/' },
  { label: 'About Us', to: '/about' },
  { label: 'Programs', to: '/programs' },
  { label: 'Admissions', to: '/admissions' },
  { label: 'Gallery', to: '/gallery' },
  { label: 'Contact Us', to: '/contact' },
]

const programs = ['Nursery', 'Primary School', 'Junior High School (JHS)']
</script>

<style scoped>
.footer {
  background: var(--color-contrast);
  color: rgba(255, 255, 255, 0.75);
}

.footer__top {
  display: grid;
  grid-template-columns: 2fr 1fr 1fr 1.5fr;
  gap: var(--space-10);
  padding-top: var(--space-16);
  padding-bottom: var(--space-16);
}

.footer__logo-wrap { display: inline-block; margin-bottom: var(--space-4); }

.footer__logo {
  width: 52px;
  height: 52px;
  object-fit: contain;
  filter: drop-shadow(0 1px 4px rgba(0,0,0,0.3));
}

.footer__school-name {
  font-family: var(--font-heading);
  font-size: 1rem;
  color: #fff;
  margin-bottom: var(--space-3);
}

.footer__tagline {
  font-size: 0.85rem;
  line-height: 1.7;
  color: rgba(255, 255, 255, 0.5);
  margin-bottom: var(--space-5);
}

.footer__social {
  display: flex;
  gap: var(--space-3);
}

.footer__social-link {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.12);
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgba(255, 255, 255, 0.6);
  transition: all var(--transition);
}

.footer__social-link:hover {
  background: var(--color-primary);
  border-color: var(--color-primary);
  color: #fff;
}

.footer__heading {
  font-family: var(--font-body);
  font-size: 0.7rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: rgba(255, 255, 255, 0.35);
  margin-bottom: var(--space-5);
}

.footer__list {
  display: flex;
  flex-direction: column;
  gap: var(--space-3);
}

.footer__link {
  font-size: 0.875rem;
  color: rgba(255, 255, 255, 0.65);
  transition: color var(--transition);
}

.footer__link:hover { color: var(--color-primary); }

.footer__hours {
  font-size: 0.85rem;
  color: rgba(255, 255, 255, 0.65);
  line-height: 1.8;
  margin: 0;
}

.footer__contact {
  display: flex;
  flex-direction: column;
  gap: var(--space-4);
}

.footer__contact li {
  display: flex;
  align-items: flex-start;
  gap: var(--space-3);
  font-size: 0.85rem;
  line-height: 1.6;
}

.footer__contact-icon { flex-shrink: 0; margin-top: 2px; }

.footer__phone { display: inline; }

.footer__bottom {
  border-top: 1px solid rgba(255, 255, 255, 0.08);
  padding: var(--space-5) 0;
}

.footer__bottom-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: var(--space-4);
  flex-wrap: wrap;
}

.footer__bottom p {
  font-size: 0.78rem;
  color: rgba(255, 255, 255, 0.35);
  margin: 0;
}

@media (max-width: 1100px) {
  .footer__top { grid-template-columns: 1fr 1fr; }
  .footer__brand { grid-column: 1 / -1; }
}

@media (max-width: 640px) {
  .footer__top { grid-template-columns: 1fr; gap: var(--space-8); }
  .footer__brand { grid-column: auto; }
  .footer__bottom-inner { flex-direction: column; text-align: center; }
}
</style>
