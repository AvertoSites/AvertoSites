<script setup>
import { RouterLink } from 'vue-router'

const services = [
  {
    icon: '💻',
    title: 'Website Design & Development',
    description:
      'Custom websites built from scratch to match your brand and business goals. We use modern technologies to create fast, responsive, and user-friendly websites.',
    features: [
      'Custom design tailored to your brand',
      'Mobile-responsive layout',
      'Fast loading times',
      'SEO-optimized structure',
      'Content management system',
      'Contact forms and integrations',
    ],
  },
  {
    icon: '🔍',
    title: 'SEO Optimization',
    description:
      "Improve your website's visibility in search engines and drive more organic traffic to your business.",
    features: [
      'Keyword research and optimization',
      'On-page SEO improvements',
      'Meta tags and descriptions',
      'Site speed optimization',
      'Mobile optimization',
      'Local SEO for businesses',
    ],
  },
  {
    icon: '🔧',
    title: 'Ongoing Maintenance',
    description:
      'Keep your website secure, updated, and performing at its best with our maintenance services.',
    features: [
      'Regular security updates',
      'Performance monitoring',
      'Backup management',
      'Content updates',
      'Technical support',
      'Monthly reports',
    ],
  },
  {
    icon: '📱',
    title: 'Social Media Integration',
    description:
      'Connect your website with your social media presence to create a cohesive online brand experience.',
    features: [
      'Social media feeds integration',
      'Share buttons and widgets',
      'Social login options',
      'Social proof displays',
      'Cross-platform consistency',
      'Social media strategy consultation',
    ],
  },
  {
    icon: '✍️',
    title: 'Content Creation Support',
    description:
      'Professional content creation to help you communicate your message effectively and engage your audience.',
    features: [
      'Website copywriting',
      'Blog post creation',
      'Product descriptions',
      'About page content',
      'SEO-optimized content',
      'Content strategy planning',
    ],
  },
  {
    icon: '🎨',
    title: 'Branding & Logo Design',
    description:
      'Create a strong visual identity for your business with professional logo design and branding services.',
    features: [
      'Custom logo design',
      'Brand color palette',
      'Typography selection',
      'Brand guidelines',
      'Business card design',
      'Social media templates',
    ],
  },
]
</script>

<template>
  <div class="services">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1>Our Services</h1>
          <p class="hero-subtitle">Comprehensive web solutions to help your business grow online</p>
        </div>
      </div>
    </section>

    <!-- Services Overview -->
    <section class="services-overview">
      <div class="container">
        <div class="section-header">
          <h2>What We Offer</h2>
          <p>
            From initial design to ongoing maintenance, we provide everything you need for a
            successful online presence
          </p>
        </div>
        <div class="services-grid">
          <div v-for="service in services" :key="service.title" class="service-card">
            <div class="service-icon">{{ service.icon }}</div>
            <h3>{{ service.title }}</h3>
            <p class="service-description">{{ service.description }}</p>
            <div class="service-features">
              <ul>
                <li v-for="feature in service.features" :key="feature">{{ feature }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Why Choose Us -->
    <section class="why-choose-us">
      <div class="container">
        <div class="section-header">
          <h2>Why Choose AvertoSites?</h2>
          <p>We're not just another web design company - we're your digital success partner</p>
        </div>

        <!-- Special Offer Banner -->
        <div class="special-offer-banner">
          <div class="offer-content">
            <div class="offer-icon">🎁</div>
            <div class="offer-text">
              <h3>Special Launch Offer</h3>
              <p>
                <strong>Choose Your FREE Bonus: 3 Months Maintenance OR Domain Registration</strong>
              </p>
              <p>
                Every new website project includes your choice: 3 months of complimentary
                maintenance OR free domain registration. Select the option that best fits your
                needs!
              </p>
            </div>
          </div>
        </div>

        <div class="benefits-grid">
          <div class="benefit-item">
            <div class="benefit-icon">⚡</div>
            <h3>Fast Turnaround</h3>
            <p>
              Get your website up and running in days, not weeks. We understand that time is money.
            </p>
          </div>
          <div class="benefit-item">
            <div class="benefit-icon">💰</div>
            <h3>Affordable Pricing</h3>
            <p>
              Professional quality at prices that work for your budget. No hidden fees or surprises.
            </p>
          </div>
          <div class="benefit-item">
            <div class="benefit-icon">🎯</div>
            <h3>Results-Driven</h3>
            <p>
              We focus on creating websites that convert visitors into customers, not just look
              pretty.
            </p>
          </div>
          <div class="benefit-item">
            <div class="benefit-icon">🤝</div>
            <h3>Ongoing Support</h3>
            <p>
              We're here for you long after your website launches. Ongoing support and maintenance
              included.
            </p>
          </div>
          <div class="benefit-item">
            <div class="benefit-icon">📱</div>
            <h3>Mobile-First</h3>
            <p>
              All our websites are designed mobile-first, ensuring they look great on every device.
            </p>
          </div>
          <div class="benefit-item">
            <div class="benefit-icon">🔒</div>
            <h3>Secure & Reliable</h3>
            <p>
              Built with security in mind. Your website and your customers' data are always
              protected.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="process">
      <div class="container">
        <div class="section-header">
          <h2>How It Works</h2>
          <p>Our simple 4-step process makes getting your website easy and stress-free</p>
        </div>
        <div class="process-timeline">
          <div class="process-step">
            <div class="step-number">1</div>
            <div class="step-content">
              <h3>Consultation</h3>
              <p>We discuss your business goals, target audience, and vision for your website.</p>
            </div>
          </div>
          <div class="process-step">
            <div class="step-number">2</div>
            <div class="step-content">
              <h3>Design & Development</h3>
              <p>We create your custom website with your feedback and approval at every stage.</p>
            </div>
          </div>
          <div class="process-step">
            <div class="step-number">3</div>
            <div class="step-content">
              <h3>Testing & Launch</h3>
              <p>
                We thoroughly test your website and launch it with all features working perfectly.
              </p>
            </div>
          </div>
          <div class="process-step">
            <div class="step-number">4</div>
            <div class="step-content">
              <h3>Support & Growth</h3>
              <p>We provide ongoing support and help you grow your online presence.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Get Started?</h2>
          <p>Let's discuss your project and find the perfect solution for your business needs.</p>
          <div class="cta-actions">
            <RouterLink to="/contact" class="cta-button primary">Start Your Project</RouterLink>
            <RouterLink to="/portfolio" class="cta-button secondary">View Our Work</RouterLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
/* Hero Section */
.hero {
  background: linear-gradient(135deg, var(--logo-blue) 0%, var(--logo-black) 100%);
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
  color: var(--light-gray);
  max-width: 600px;
  margin: 0 auto;
}

/* Services Overview */
.services-overview {
  padding: 5rem 0;
  background: var(--off-white);
}

.section-header {
  text-align: center;
  margin-bottom: 3rem;
}

.section-header h2 {
  font-size: 2.5rem;
  color: var(--logo-black);
  margin-bottom: 1rem;
}

.section-header p {
  font-size: 1.1rem;
  color: var(--gray);
  max-width: 600px;
  margin: 0 auto;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
}

.service-card {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.service-card:hover {
  transform: translateY(-5px);
}

.service-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.service-card h3 {
  color: var(--logo-black);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.service-description {
  color: var(--gray);
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.service-features ul {
  list-style: none;
  margin-bottom: 1.5rem;
}

.service-features li {
  color: var(--dark-gray);
  margin-bottom: 0.5rem;
  padding-left: 1.5rem;
  position: relative;
}

.service-features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--logo-green);
  font-weight: bold;
}

/* Why Choose Us */
.why-choose-us {
  padding: 5rem 0;
  background: var(--off-white);
}

.special-offer-banner {
  background: linear-gradient(135deg, var(--logo-blue) 0%, var(--logo-black) 100%);
  color: white;
  padding: 2rem;
  border-radius: 16px;
  margin-bottom: 3rem;
  box-shadow: 0 10px 30px rgba(30, 64, 175, 0.2);
  position: relative;
  overflow: hidden;
}

.special-offer-banner::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grain" width="100" height="100" patternUnits="userSpaceOnUse"><circle cx="25" cy="25" r="1" fill="white" opacity="0.1"/><circle cx="75" cy="75" r="1" fill="white" opacity="0.1"/><circle cx="50" cy="10" r="0.5" fill="white" opacity="0.1"/><circle cx="10" cy="60" r="0.5" fill="white" opacity="0.1"/><circle cx="90" cy="40" r="0.5" fill="white" opacity="0.1"/></pattern></defs><rect width="100" height="100" fill="url(%23grain)"/></svg>');
  opacity: 0.3;
}

.offer-content {
  display: flex;
  align-items: center;
  gap: 2rem;
  position: relative;
  z-index: 1;
}

.offer-icon {
  font-size: 3rem;
  flex-shrink: 0;
}

.offer-text h3 {
  color: white;
  font-size: 1.5rem;
  margin-bottom: 0.5rem;
  font-weight: 700;
}

.offer-text p {
  color: var(--light-gray);
  line-height: 1.6;
  margin-bottom: 0.5rem;
}

.offer-text p:last-child {
  margin-bottom: 0;
}

.offer-text strong {
  color: var(--logo-green);
  font-weight: 600;
}

.benefits-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.benefit-item {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.benefit-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.benefit-item h3 {
  color: var(--logo-black);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.benefit-item p {
  color: var(--gray);
  line-height: 1.6;
}

/* Process Section */
.process {
  padding: 5rem 0;
}

.process-timeline {
  max-width: 800px;
  margin: 0 auto;
}

.process-step {
  display: flex;
  align-items: flex-start;
  gap: 2rem;
  margin-bottom: 3rem;
  position: relative;
}

.process-step:not(:last-child)::after {
  content: '';
  position: absolute;
  left: 30px;
  top: 60px;
  bottom: -3rem;
  width: 2px;
  background: linear-gradient(to bottom, var(--logo-blue), var(--logo-green));
}

.step-number {
  width: 60px;
  height: 60px;
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  font-weight: 700;
  flex-shrink: 0;
}

.step-content h3 {
  color: var(--logo-black);
  margin-bottom: 0.5rem;
  font-size: 1.25rem;
}

.step-content p {
  color: var(--gray);
  line-height: 1.6;
}

/* CTA Section */
.cta-section {
  padding: 5rem 0;
  background: linear-gradient(135deg, var(--logo-blue) 0%, var(--logo-black) 100%);
  color: white;
  text-align: center;
}

.cta-content h2 {
  font-size: 2.5rem;
  margin-bottom: 1rem;
}

.cta-content p {
  font-size: 1.1rem;
  color: var(--light-gray);
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
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
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
  color: var(--logo-black);
}

/* Responsive Design */
@media (max-width: 768px) {
  .services-grid {
    grid-template-columns: 1fr;
  }

  .special-offer-banner {
    padding: 1.5rem;
  }

  .offer-content {
    flex-direction: column;
    text-align: center;
    gap: 1rem;
  }

  .offer-text h3 {
    font-size: 1.25rem;
  }

  .benefits-grid {
    grid-template-columns: 1fr;
  }

  .process-step {
    flex-direction: column;
    text-align: center;
  }

  .process-step::after {
    display: none;
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

  .service-card,
  .benefit-item {
    padding: 1.5rem;
  }
}
</style>
