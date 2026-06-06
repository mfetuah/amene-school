<template>
  <header class="header" :class="{ 'header--scrolled': isScrolled }">
    <div class="header__inner container">
      <NuxtLink to="/" class="header__logo">
        <img src="/images/amene-tranparent-logo.png" alt="Amene International School" />
        <span class="header__name">AMENE International <em>School</em></span>
      </NuxtLink>

      <nav class="header__nav" :class="{ 'header__nav--open': isOpen }">
        <ul class="header__links">
          <li v-for="link in links" :key="link.to">
            <NuxtLink :to="link.to" class="header__link" @click="isOpen = false">
              {{ link.label }}
            </NuxtLink>
          </li>
        </ul>
        <NuxtLink to="/admissions" class="btn btn-primary header__enroll" @click="isOpen = false">
          Apply Now
        </NuxtLink>
      </nav>

      <button
        class="header__burger"
        :class="{ 'header__burger--open': isOpen }"
        @click="isOpen = !isOpen"
        aria-label="Toggle menu"
      >
        <span /><span /><span />
      </button>
    </div>
  </header>
</template>

<script setup lang="ts">
const isOpen = ref(false)
const isScrolled = ref(false)

const links = [
  { label: 'Home', to: '/' },
  { label: 'About', to: '/about' },
  { label: 'Programs', to: '/programs' },
  { label: 'Admissions', to: '/admissions' },
  { label: 'Gallery', to: '/gallery' },
  { label: 'Contact', to: '/contact' },
]

onMounted(() => {
  const handler = () => { isScrolled.value = window.scrollY > 60 }
  window.addEventListener('scroll', handler, { passive: true })
  onUnmounted(() => window.removeEventListener('scroll', handler))
})
</script>

<style scoped>
.header {
  position: fixed;
  inset: 0 0 auto 0;
  z-index: 200;
  background: rgba(249, 249, 249, 0.97);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid transparent;
  transition: border-color var(--transition), box-shadow var(--transition);
}

.header--scrolled {
  border-bottom-color: var(--color-border);
  box-shadow: var(--shadow-sm);
}

.header__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 72px;
  gap: var(--space-8);
}

.header__logo {
  display: flex;
  align-items: center;
  gap: var(--space-3);
  flex-shrink: 0;
}

.header__logo img {
  width: 42px;
  height: 42px;
  object-fit: contain;
}

.header__name {
  font-family: var(--font-heading);
  font-size: 0.9rem;
  line-height: 1.35;
  color: var(--color-contrast);
}

.header__name em {
  font-style: italic;
  color: var(--color-primary);
  display: block;
}

.header__nav {
  display: flex;
  align-items: center;
  gap: var(--space-8);
}

.header__links {
  display: flex;
  align-items: center;
  gap: var(--space-5);
}

.header__link {
  font-size: 0.875rem;
  font-weight: 500;
  color: var(--color-contrast);
  position: relative;
  padding-bottom: 2px;
  transition: color var(--transition);
}

.header__link::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  right: 0;
  height: 2px;
  background: var(--color-primary);
  transform: scaleX(0);
  transform-origin: left;
  transition: transform var(--transition);
}

.header__link:hover,
.header__link.router-link-exact-active {
  color: var(--color-primary);
}

.header__link:hover::after,
.header__link.router-link-exact-active::after {
  transform: scaleX(1);
}

.header__burger {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 40px;
  height: 40px;
  padding: var(--space-2);
  background: none;
  border: none;
  cursor: pointer;
  flex-shrink: 0;
}

.header__burger span {
  display: block;
  width: 100%;
  height: 2px;
  background: var(--color-contrast);
  border-radius: 2px;
  transition: all var(--transition);
  transform-origin: center;
}

.header__burger--open span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.header__burger--open span:nth-child(2) { opacity: 0; transform: scaleX(0); }
.header__burger--open span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

@media (max-width: 960px) {
  .header__burger { display: flex; }
  .header__enroll { display: none; }

  .header__nav {
    position: fixed;
    top: 72px;
    left: 0;
    right: 0;
    background: var(--color-white);
    border-bottom: 1px solid var(--color-border);
    flex-direction: column;
    align-items: stretch;
    gap: 0;
    padding: var(--space-4) 0 var(--space-6);
    box-shadow: var(--shadow-md);
    transform: translateY(-110%);
    opacity: 0;
    pointer-events: none;
    transition: transform var(--transition), opacity var(--transition);
  }

  .header__nav--open {
    transform: translateY(0);
    opacity: 1;
    pointer-events: all;
  }

  .header__links {
    flex-direction: column;
    align-items: stretch;
    gap: 0;
  }

  .header__link {
    display: block;
    padding: var(--space-3) var(--gutter);
    font-size: 1rem;
    border-bottom: 1px solid var(--color-border);
  }

  .header__link::after { display: none; }
}
</style>
