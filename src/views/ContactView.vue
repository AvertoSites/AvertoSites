<script setup>
import { ref } from 'vue'
import emailjs from '@emailjs/browser'

const formData = ref({
  name: '',
  email: '',
  phone: '',
  company: '',
  message: '',
  budget: '',
  projectType: '',
})

const isSending = ref(false)
const sendSuccess = ref(false)
const sendError = ref(false)

// TODO: Replace these with your actual EmailJS credentials
const SERVICE_ID = 'service_99cmiz3'
const TEMPLATE_ID = 'template_v7gyg3f'
const PUBLIC_KEY = 'hYCUhwMq4FFMIpUFe'

const budgetOptions = [
  'Under $1,000',
  '$1,000 - $2,500',
  '$2,500 - $5,000',
  '$5,000 - $10,000',
  '$10,000+',
]

const projectTypes = [
  'Website Design & Development',
  'E-commerce Website',
  'Website Redesign',
  'SEO Optimization',
  'Maintenance & Support',
  'Branding & Logo Design',
  'Other',
]

const handleSubmit = async (e) => {
  e.preventDefault()
  isSending.value = true
  sendSuccess.value = false
  sendError.value = false

  try {
    await emailjs.send(
      SERVICE_ID,
      TEMPLATE_ID,
      {
        name: formData.value.name,
        email: formData.value.email,
        phone: formData.value.phone,
        company: formData.value.company,
        message: formData.value.message,
        budget: formData.value.budget,
        projectType: formData.value.projectType,
      },
      PUBLIC_KEY,
    )
    sendSuccess.value = true
    // Reset form
    formData.value = {
      name: '',
      email: '',
      phone: '',
      company: '',
      message: '',
      budget: '',
      projectType: '',
    }
  } catch (error) {
    sendError.value = true
  } finally {
    isSending.value = false
  }
}
</script>

<template>
  <div class="contact">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1>Get In Touch</h1>
          <p class="hero-subtitle">
            Ready to start your project? Let's discuss how we can help bring your vision to life.
          </p>
        </div>
      </div>
    </section>

    <!-- Contact Content -->
    <section class="contact-content">
      <div class="container">
        <div class="contact-grid">
          <!-- Contact Form -->
          <div class="contact-form-section">
            <h2>Start Your Project</h2>
            <p>
              Fill out the form below and we'll get back to you within 24 hours with a custom quote.
            </p>

            <form @submit="handleSubmit" class="contact-form">
              <div class="form-row">
                <div class="form-group">
                  <label for="name">Full Name *</label>
                  <input
                    type="text"
                    id="name"
                    v-model="formData.name"
                    required
                    placeholder="Your full name"
                  />
                </div>
                <div class="form-group">
                  <label for="email">Email Address *</label>
                  <input
                    type="email"
                    id="email"
                    v-model="formData.email"
                    required
                    placeholder="your@email.com"
                  />
                </div>
              </div>

              <div class="form-row">
                <div class="form-group">
                  <label for="phone">Phone Number</label>
                  <input
                    type="tel"
                    id="phone"
                    v-model="formData.phone"
                    placeholder="(123) 456-7890"
                  />
                </div>
                <div class="form-group">
                  <label for="company">Company Name</label>
                  <input
                    type="text"
                    id="company"
                    v-model="formData.company"
                    placeholder="Your company name"
                  />
                </div>
              </div>

              <div class="form-row">
                <div class="form-group">
                  <label for="projectType">Project Type *</label>
                  <select id="projectType" v-model="formData.projectType" required>
                    <option value="">Select project type</option>
                    <option v-for="type in projectTypes" :key="type" :value="type">
                      {{ type }}
                    </option>
                  </select>
                </div>
                <div class="form-group">
                  <label for="budget">Budget Range</label>
                  <select id="budget" v-model="formData.budget">
                    <option value="">Select budget range</option>
                    <option v-for="budget in budgetOptions" :key="budget" :value="budget">
                      {{ budget }}
                    </option>
                  </select>
                </div>
              </div>

              <div class="form-group">
                <label for="message">Project Details *</label>
                <textarea
                  id="message"
                  v-model="formData.message"
                  required
                  rows="6"
                  placeholder="Tell us about your project, goals, and any specific requirements..."
                ></textarea>
              </div>

              <button type="submit" class="submit-btn" :disabled="isSending">
                {{ isSending ? 'Sending...' : 'Send Message' }}
              </button>
              <p v-if="sendSuccess" style="color: green">Message sent successfully!</p>
              <p v-if="sendError" style="color: red">Failed to send message. Please try again.</p>
            </form>
          </div>

          <!-- Contact Information -->
          <div class="contact-info-section">
            <h2>Contact Information</h2>
            <p>Get in touch with us through any of these channels. We're here to help!</p>

            <div class="contact-methods">
              <div class="contact-method">
                <div class="method-icon">📧</div>
                <div class="method-content">
                  <h3>Email</h3>
                  <p>contact.avertosites@gmail.com</p>
                  <span class="method-note">We respond within 24 hours</span>
                </div>
              </div>

              <div class="contact-method">
                <div class="method-icon">📞</div>
                <div class="method-content">
                  <h3>Phone</h3>
                  <p>+1 (647) 509-8275</p>
                  <p>+1 (753) 886-1887</p>
                  <span class="method-note">Available Mon-Sun, 8AM-7PM EST</span>
                </div>
              </div>

              <div class="contact-method">
                <div class="method-icon">💬</div>
                <div class="method-content">
                  <h3>Social Media & Messaging</h3>
                  <div class="social-links">
                    <a
                      href="https://www.instagram.com/avertosites?igsh=OGwwNnZlaXR2eHcz&utm_source=qr"
                      target="_blank"
                      rel="noopener"
                      >Instagram</a
                    >
                    <a href="https://www.tiktok.com/@avertosites" target="_blank" rel="noopener"
                      >TikTok</a
                    >
                    <a href="https://wa.me/16475098275" target="_blank" rel="noopener">WhatsApp</a>
                  </div>
                  <span class="method-note">Follow us for updates and tips</span>
                </div>
              </div>
              <div class="contact-method">
                <div class="method-icon">📍</div>
                <div class="method-content">
                  <h3>Google Business</h3>
                  <a href="https://share.google/h9sPWhMvc4CzcqKtc" target="_blank" rel="noopener"
                    >View on Google Business</a
                  >
                  <span class="method-note">See our reviews and location</span>
                </div>
              </div>
            </div>

            <div class="business-hours">
              <h3>Business Hours</h3>
              <div class="hours-grid">
                <div class="hours-item">
                  <span class="day">Monday - Friday</span>
                  <span class="time">8:00 AM - 7:00 PM EST</span>
                </div>
                <div class="hours-item">
                  <span class="day">Saturday</span>
                  <span class="time">8:00 AM - 7:00 PM EST</span>
                </div>
                <div class="hours-item">
                  <span class="day">Sunday</span>
                  <span class="time">8:00 AM - 7:00 PM EST</span>
                </div>
              </div>
            </div>

            <div class="response-time">
              <h3>Response Time</h3>
              <div class="response-info">
                <div class="response-item">
                  <span class="response-label">Email Response</span>
                  <span class="response-time">Within 24 hours</span>
                </div>
                <div class="response-item">
                  <span class="response-label">Phone Response</span>
                  <span class="response-time">Same day</span>
                </div>
                <div class="response-item">
                  <span class="response-label">Project Quote</span>
                  <span class="response-time">Within 24 hours</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- FAQ Section -->
    <section class="faq-section">
      <div class="container">
        <div class="section-header">
          <h2>Frequently Asked Questions</h2>
          <p>Get answers to common questions about our services and process</p>
        </div>

        <div class="faq-grid">
          <div class="faq-item">
            <h3>How long does it take to build a website?</h3>
            <p>
              Most websites are completed within 7-14 days, depending on complexity. We'll provide a
              specific timeline during our consultation.
            </p>
          </div>

          <div class="faq-item">
            <h3>Do you provide ongoing support?</h3>
            <p>
              Yes! We offer maintenance packages and ongoing support to keep your website secure,
              updated, and performing at its best.
            </p>
          </div>

          <div class="faq-item">
            <h3>Can you redesign my existing website?</h3>
            <p>
              Absolutely! We specialize in website redesigns and can modernize your existing site
              while preserving your content and SEO value.
            </p>
          </div>

          <div class="faq-item">
            <h3>Do you work with small businesses?</h3>
            <p>
              Yes! We love working with small businesses and entrepreneurs. We offer affordable
              packages designed specifically for growing businesses.
            </p>
          </div>

          <div class="faq-item">
            <h3>What if I need changes after launch?</h3>
            <p>
              We include 30 days of free revisions after launch. After that, we offer affordable
              maintenance packages for ongoing updates.
            </p>
          </div>

          <div class="faq-item">
            <h3>Do you provide hosting and domain services?</h3>
            <p>
              We can help you set up hosting and domain registration, or work with your existing
              provider. We recommend reliable, fast hosting for optimal performance.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Get Started?</h2>
          <p>
            Don't wait to transform your online presence. Contact us today and let's create
            something amazing together!
          </p>
          <div class="cta-actions">
            <a href="mailto:contact.avertosites@gmail.com" class="cta-button primary"
              >Email Us Now</a
            >
            <a href="tel:+16475098275" class="cta-button secondary">Call Us</a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
/* Hero Section */
.hero {
  background: linear-gradient(135deg, #1e3a8a 0%, #0f172a 100%);
  color: white;
  padding: 4rem 0;
  text-align: center;
}

.hero h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: 700;
}

.hero-subtitle {
  font-size: 1.25rem;
  color: #cbd5e1;
  max-width: 600px;
  margin: 0 auto;
}

/* Contact Content */
.contact-content {
  padding: 5rem 0;
  background: #f8fafc;
}

.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

/* Contact Form */
.contact-form-section h2 {
  color: #1e293b;
  font-size: 2rem;
  margin-bottom: 1rem;
}

.contact-form-section > p {
  color: #64748b;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.contact-form {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  max-width: 920px;
  width: 100%;
  margin-left: auto;
  margin-right: auto;
}

.form-row {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin-bottom: 1rem;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  color: #374151;
  font-weight: 600;
  margin-bottom: 0.5rem;
}

.form-group input,
.form-group select,
.form-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus {
  outline: none;
  border-color: #06b6d4;
}

.form-group textarea {
  resize: vertical;
  min-height: 120px;
}

.submit-btn {
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  color: white;
  padding: 1rem 2rem;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: transform 0.3s ease;
  width: 100%;
}

.submit-btn:hover {
  transform: translateY(-2px);
}

/* Contact Information */
.contact-info-section h2 {
  color: #1e293b;
  font-size: 2rem;
  margin-bottom: 1rem;
}

.contact-info-section > p {
  color: #64748b;
  margin-bottom: 2rem;
  line-height: 1.6;
}

.contact-methods {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  margin-bottom: 2rem;
}

.contact-method {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
}

.method-icon {
  font-size: 2rem;
  flex-shrink: 0;
}

.method-content h3 {
  color: #1e293b;
  margin-bottom: 0.5rem;
  font-size: 1.1rem;
}

.method-content p {
  color: #374151;
  margin-bottom: 0.25rem;
}

.method-note {
  color: #64748b;
  font-size: 0.875rem;
  font-style: italic;
}

.social-links {
  display: flex;
  gap: 1rem;
  margin-bottom: 0.25rem;
}

.social-links a {
  color: #06b6d4;
  text-decoration: none;
  font-weight: 500;
}

.social-links a:hover {
  text-decoration: underline;
}

/* Business Hours */
.business-hours {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  margin-bottom: 2rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.business-hours h3 {
  color: #1e293b;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.hours-grid {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.hours-item {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0;
  border-bottom: 1px solid #f1f5f9;
}

.hours-item:last-child {
  border-bottom: none;
}

.day {
  color: #374151;
  font-weight: 500;
}

.time {
  color: #64748b;
}

/* Response Time */
.response-time {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.response-time h3 {
  color: #1e293b;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.response-info {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.response-item {
  display: flex;
  justify-content: space-between;
  padding: 0.5rem 0;
  border-bottom: 1px solid #f1f5f9;
}

.response-item:last-child {
  border-bottom: none;
}

.response-label {
  color: #374151;
  font-weight: 500;
}

.response-time {
  color: #06b6d4;
  font-weight: 600;
}

/* FAQ Section */
.faq-section {
  padding: 5rem 0;
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-header h2 {
  font-size: 2.5rem;
  color: #1e293b;
  margin-bottom: 1rem;
}

.section-header p {
  font-size: 1.1rem;
  color: #64748b;
  max-width: 600px;
  margin: 0 auto;
}

.faq-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 2rem;
}

.faq-item {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.faq-item h3 {
  color: #1e293b;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.faq-item p {
  color: #64748b;
  line-height: 1.6;
}

/* CTA Section */
.cta-section {
  padding: 5rem 0;
  background: linear-gradient(135deg, #1e3a8a 0%, #0f172a 100%);
  color: white;
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.cta-content p {
  font-size: 1.1rem;
  color: #cbd5e1;
  margin-bottom: 2rem;
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.cta-actions {
  display: flex;
  gap: 1rem;
  justify-content: center;
  flex-wrap: wrap;
}

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: transform 0.3s ease;
  border: 2px solid transparent;
}

.cta-button.primary {
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  color: white;
}

.cta-button.primary:hover {
  transform: translateY(-2px);
}

.cta-button.secondary {
  background: transparent;
  color: white;
  border-color: white;
}

.cta-button.secondary:hover {
  background: white;
  color: #0f172a;
}

/* Responsive Design */
@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .form-row {
    grid-template-columns: 1fr;
  }

  .faq-grid {
    grid-template-columns: 1fr;
  }

  .hero h1 {
    font-size: 2.5rem;
  }

  .section-header h2 {
    font-size: 2rem;
  }

  .cta-content h2 {
    font-size: 2rem;
  }

  .cta-actions {
    flex-direction: column;
    align-items: center;
  }
}

@media (max-width: 480px) {
  .hero h1 {
    font-size: 2rem;
  }

  .contact-form {
    padding: 1.5rem;
  }

  .contact-method {
    flex-direction: column;
    text-align: center;
  }

  .hours-item,
  .response-item {
    flex-direction: column;
    gap: 0.25rem;
  }
}
</style>
