<template>
  <div>
    <div class="page-hero">
      <div class="container">
        <p class="page-hero__label">Join Our School</p>
        <h1 class="page-hero__title">Admissions</h1>
        <p class="page-hero__subtitle">
          We welcome applications for all academic levels. Our admissions process is simple, clear, and designed to give your child the best start.
        </p>
      </div>
    </div>

    <section class="admissions section">
      <div class="container">
        <div class="admissions__grid">
          <!-- Left column: info -->
          <div class="admissions__info">

            <!-- Overview -->
            <div class="admissions__block">
              <h2>Admissions Overview</h2>
              <p>
                Amene International School accepts applications from children of all ability levels.
                We currently offer entry at three academic levels — Nursery, Primary, and Junior High School —
                with admissions open year-round for the current and upcoming academic year.
              </p>
              <div class="admissions__overview-tags">
                <span v-for="tag in overviewTags" :key="tag" class="admissions__tag">{{ tag }}</span>
              </div>
            </div>

            <!-- Process -->
            <div class="admissions__block">
              <h2>Admission Process</h2>
              <p class="admissions__hint">Follow these 5 simple steps to enroll your child:</p>
              <div class="admissions__steps">
                <div v-for="(step, i) in steps" :key="step.title" class="admissions__step">
                  <div class="admissions__step-num">{{ i + 1 }}</div>
                  <div class="admissions__step-body">
                    <h3>{{ step.title }}</h3>
                    <p>{{ step.desc }}</p>
                  </div>
                </div>
              </div>
            </div>

            <!-- Requirements -->
            <div class="admissions__block">
              <h2>Required Documents</h2>
              <ul class="admissions__docs">
                <li v-for="doc in docs" :key="doc.item">
                  <span class="admissions__check">✓</span>
                  <div>
                    <strong>{{ doc.item }}</strong>
                    <span v-if="doc.note"> — {{ doc.note }}</span>
                  </div>
                </li>
              </ul>
            </div>

            <!-- Fees -->
            <div class="admissions__block admissions__fees">
              <h2>Fees Overview</h2>
              <p>
                We are committed to making quality education accessible. Our fees cover:
              </p>
              <ul class="admissions__fee-list">
                <li><span>📋</span> Application / Admission form fee</li>
                <li><span>📅</span> Termly tuition (contact us for current rates)</li>
                <li><span>👕</span> School uniforms and books (additional)</li>
                <li><span>🚌</span> Optional school bus service</li>
              </ul>
              <p class="admissions__fees-note">
                For a full and current fee schedule, please contact our admissions office directly or visit the school.
              </p>
            </div>

          </div>

          <!-- Right column: CTA + form -->
          <div class="admissions__form-col">
            <div class="admissions__cta-card">
              <h2>Ready to Apply?</h2>
              <p>Contact us directly or fill in this enquiry form and our admissions team will reach out within 24 hours.</p>

              <div class="admissions__direct-contact">
                <a href="tel:+233551569990" class="admissions__contact-btn">
                  <span>📞</span> 055 156 9990
                </a>
                <a href="tel:+233599449080" class="admissions__contact-btn">
                  <span>📞</span> 059 944 9080
                </a>
                <a href="mailto:ameneedu@gmail.com" class="admissions__contact-btn admissions__contact-btn--email">
                  <span>✉️</span> ameneedu@gmail.com
                </a>
              </div>

              <div class="admissions__divider">or send an enquiry</div>

              <form class="admissions__form" @submit.prevent="submitForm">
                <div class="form-field">
                  <label>Parent / Guardian Name *</label>
                  <input v-model="form.parentName" type="text" placeholder="Full name" required />
                </div>
                <div class="form-field">
                  <label>Phone Number *</label>
                  <input v-model="form.phone" type="tel" placeholder="055 000 0000" required />
                </div>
                <div class="form-field">
                  <label>Email Address</label>
                  <input v-model="form.email" type="email" placeholder="your@email.com" />
                </div>
                <div class="form-field">
                  <label>Child's Name *</label>
                  <input v-model="form.childName" type="text" placeholder="Child's full name" required />
                </div>
                <div class="form-field">
                  <label>Program Applying For *</label>
                  <select v-model="form.program" required>
                    <option value="">Select a program...</option>
                    <option v-for="p in programOptions" :key="p" :value="p">{{ p }}</option>
                  </select>
                </div>
                <div class="form-field">
                  <label>Additional Message</label>
                  <textarea v-model="form.message" rows="3" placeholder="Any questions or special requirements..."></textarea>
                </div>
                <div v-if="submitted" class="admissions__success">
                  ✓ Thank you! Our admissions team will contact you within 24 hours.
                </div>
                <button v-else type="submit" class="btn btn-primary" style="width:100%;">
                  Submit Enquiry
                </button>
              </form>
            </div>
          </div>
        </div>
      </div>
    </section>

    <SectionsCtaSection />
  </div>
</template>

<script setup lang="ts">
useSeoMeta({
  title: 'Admissions — AMENE International School',
  description: 'Apply to Amene International School. Enroll your child in our Nursery, Primary, or Junior High School programs in Birim North, Ghana.',
})

const submitted = ref(false)
const form = reactive({ parentName: '', phone: '', email: '', childName: '', program: '', message: '' })

const overviewTags = ['Nursery', 'Primary School', 'Junior High School', 'All Ability Levels', 'Year-Round Applications']

const steps = [
  { title: 'Purchase Admission Form', desc: 'Visit the school or contact us to obtain the official admission form. A small form fee applies.' },
  { title: 'Submit Completed Form', desc: 'Return the completed form along with all required supporting documents to the admissions office.' },
  { title: 'Entrance Assessment / Interview', desc: 'Depending on the level, your child may be invited for a brief, friendly assessment or orientation visit.' },
  { title: 'Admission Decision', desc: 'Our team will review the application and inform you of the admission decision promptly.' },
  { title: 'Enrolment & Orientation', desc: 'Upon acceptance, complete the enrolment process and attend our welcome orientation session.' },
]

const docs = [
  { item: 'Birth Certificate', note: 'Original or certified copy' },
  { item: 'Previous School Report', note: 'If applicable — most recent academic report' },
  { item: 'Passport-sized Photograph', note: '2 recent photos of the child' },
  { item: 'Medical Report', note: 'If any known medical conditions' },
]

const programOptions = ['Nursery', 'Primary School (Class 1–6)', 'Junior High School (JHS 1–3)']

function submitForm() { submitted.value = true }
</script>

<style scoped>
.admissions__grid {
  display: grid;
  grid-template-columns: 1.1fr 1fr;
  gap: var(--space-12);
  align-items: flex-start;
}

.admissions__block {
  margin-bottom: var(--space-10);
  padding-bottom: var(--space-10);
  border-bottom: 1px solid var(--color-border);
}

.admissions__block:last-child { border-bottom: none; margin-bottom: 0; padding-bottom: 0; }

.admissions__block h2 { font-size: clamp(1.4rem, 3vw, 1.9rem); margin-bottom: var(--space-4); }
.admissions__block > p { font-size: 0.95rem; line-height: 1.75; margin-bottom: var(--space-4); }

.admissions__overview-tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-2);
  margin-top: var(--space-4);
}

.admissions__tag {
  background: rgba(216, 97, 60, 0.1);
  color: var(--color-primary);
  border: 1px solid rgba(216, 97, 60, 0.2);
  font-size: 0.8rem;
  font-weight: 600;
  padding: var(--space-1) var(--space-3);
  border-radius: 99px;
}

.admissions__hint { margin-bottom: var(--space-6) !important; }

.admissions__steps { display: flex; flex-direction: column; gap: var(--space-5); }

.admissions__step {
  display: flex;
  gap: var(--space-4);
  align-items: flex-start;
}

.admissions__step-num {
  width: 36px; height: 36px;
  border-radius: 50%;
  background: var(--color-primary);
  color: #fff;
  display: flex; align-items: center; justify-content: center;
  font-weight: 700; font-size: 0.9rem;
  flex-shrink: 0; margin-top: 2px;
}

.admissions__step-body h3 {
  font-size: 0.95rem;
  font-family: var(--font-body);
  font-weight: 600;
  margin-bottom: var(--space-1);
  color: var(--color-contrast);
}

.admissions__step-body p { font-size: 0.875rem; }

.admissions__docs { display: flex; flex-direction: column; gap: var(--space-3); }

.admissions__docs li {
  display: flex;
  align-items: flex-start;
  gap: var(--space-3);
  font-size: 0.9rem;
}

.admissions__check {
  width: 22px; height: 22px;
  background: var(--color-secondary);
  border-radius: 50%;
  display: flex; align-items: center; justify-content: center;
  font-size: 0.7rem; font-weight: 700;
  flex-shrink: 0; margin-top: 2px;
  color: var(--color-contrast);
}

.admissions__docs strong { color: var(--color-contrast); }

.admissions__fees p { font-size: 0.9rem !important; }

.admissions__fee-list {
  display: flex; flex-direction: column; gap: var(--space-3);
  margin: var(--space-4) 0;
}

.admissions__fee-list li {
  display: flex; align-items: center; gap: var(--space-3);
  font-size: 0.875rem; color: var(--color-muted);
}

.admissions__fees-note {
  font-size: 0.85rem !important;
  color: var(--color-muted);
  font-style: italic;
}

.admissions__cta-card {
  background: var(--color-white);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-lg);
  padding: var(--space-8);
  box-shadow: var(--shadow-sm);
  position: sticky;
  top: calc(72px + var(--space-6));
}

.admissions__cta-card h2 { font-size: 1.5rem; margin-bottom: var(--space-2); }
.admissions__cta-card > p { font-size: 0.875rem; margin-bottom: var(--space-5); }

.admissions__direct-contact {
  display: flex; flex-direction: column; gap: var(--space-3);
  margin-bottom: var(--space-5);
}

.admissions__contact-btn {
  display: flex; align-items: center; gap: var(--space-3);
  padding: var(--space-3) var(--space-4);
  background: var(--color-base);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-sm);
  font-size: 0.9rem; font-weight: 600;
  color: var(--color-contrast);
  transition: all var(--transition);
}

.admissions__contact-btn:hover {
  border-color: var(--color-primary);
  background: rgba(216, 97, 60, 0.05);
  color: var(--color-primary);
}

.admissions__contact-btn--email { font-size: 0.82rem; }

.admissions__divider {
  text-align: center;
  font-size: 0.8rem;
  color: var(--color-muted);
  position: relative;
  margin: var(--space-5) 0;
}

.admissions__divider::before,
.admissions__divider::after {
  content: '';
  position: absolute;
  top: 50%;
  width: 38%;
  height: 1px;
  background: var(--color-border);
}

.admissions__divider::before { left: 0; }
.admissions__divider::after { right: 0; }

.admissions__form { display: flex; flex-direction: column; gap: var(--space-4); }

.form-field { display: flex; flex-direction: column; gap: var(--space-2); }

.form-field label { font-size: 0.8rem; font-weight: 500; color: var(--color-contrast); }

.form-field input, .form-field select, .form-field textarea {
  width: 100%;
  padding: 0.65rem var(--space-4);
  border: 1px solid var(--color-border);
  border-radius: var(--radius-sm);
  font-family: var(--font-body);
  font-size: 0.875rem;
  background: var(--color-base);
  color: var(--color-contrast);
  transition: border-color var(--transition);
}

.form-field input:focus, .form-field select:focus, .form-field textarea:focus {
  outline: none; border-color: var(--color-primary);
}

.admissions__success {
  background: var(--color-secondary);
  color: var(--color-contrast);
  padding: var(--space-4);
  border-radius: var(--radius-sm);
  text-align: center;
  font-weight: 600;
  font-size: 0.9rem;
}

@media (max-width: 1024px) {
  .admissions__grid { grid-template-columns: 1fr; }
  .admissions__cta-card { position: static; }
}
</style>
