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
    price: 'Starting at $999',
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
    price: 'Starting at $299',
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
    price: 'Starting at $99/month',
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
    price: 'Starting at $199',
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
    price: 'Starting at $150/page',
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
    price: 'Starting at $399',
  },
]

const packages = [
  {
    name: 'Starter',
    price: '$999',
    description: 'Perfect for small businesses and startups',
    features: [
      '5-page custom website',
      'Mobile responsive design',
      'Contact form',
      'Basic SEO setup',
      '1 month of support',
      'Training session',
    ],
    popular: false,
  },
  {
    name: 'Professional',
    price: '$1,999',
    description: 'Ideal for growing businesses',
    features: [
      '10-page custom website',
      'Advanced SEO optimization',
      'E-commerce integration',
      'Social media integration',
      '3 months of support',
      'Content creation (5 pages)',
      'Analytics setup',
    ],
    popular: true,
  },
  {
    name: 'Enterprise',
    price: '$3,999',
    description: 'For established businesses with complex needs',
    features: [
      'Unlimited pages',
      'Custom functionality',
      'Advanced integrations',
      'Priority support',
      '6 months of maintenance',
      'Full content creation',
      'Performance optimization',
      'Security hardening',
    ],
    popular: false,
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
            <div class="service-price">{{ service.price }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Pricing Packages -->
    <section class="pricing">
      <div class="container">
        <div class="section-header">
          <h2>Choose Your Package</h2>
          <p>Select the perfect package for your business needs and budget</p>
        </div>
        <div class="pricing-grid">
          <div
            v-for="servicePackage in packages"
            :key="servicePackage.name"
            class="pricing-card"
            :class="{ popular: servicePackage.popular }"
          >
            <div v-if="servicePackage.popular" class="popular-badge">Most Popular</div>
            <div class="package-header">
              <h3>{{ servicePackage.name }}</h3>
              <div class="package-price">
                <span class="price">{{ servicePackage.price }}</span>
              </div>
              <p class="package-description">{{ servicePackage.description }}</p>
            </div>
            <div class="package-features">
              <ul>
                <li v-for="feature in servicePackage.features" :key="feature">
                  <span class="checkmark">✓</span>
                  {{ feature }}
                </li>
              </ul>
            </div>
            <RouterLink to="/contact" class="package-cta">Get Started</RouterLink>
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

.service-price {
  font-size: 1.25rem;
  font-weight: 600;
  color: var(--logo-blue);
  text-align: center;
  padding-top: 1rem;
  border-top: 1px solid #e2e8f0;
}

/* Pricing Section */
.pricing {
  padding: 5rem 0;
}

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 1000px;
  margin: 0 auto;
}

.pricing-card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  position: relative;
  transition: transform 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-5px);
}

.pricing-card.popular {
  border: 2px solid var(--logo-green);
  transform: scale(1.05);
}

.popular-badge {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 600;
}

.package-header {
  text-align: center;
  margin-bottom: 2rem;
}

.package-header h3 {
  color: var(--logo-black);
  font-size: 1.5rem;
  margin-bottom: 1rem;
}

.package-price {
  margin-bottom: 1rem;
}

.price {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--logo-blue);
}

.package-description {
  color: var(--gray);
  font-size: 0.9rem;
}

.package-features ul {
  list-style: none;
  margin-bottom: 2rem;
}

.package-features li {
  color: var(--dark-gray);
  margin-bottom: 0.75rem;
  display: flex;
  align-items: center;
}

.checkmark {
  color: var(--logo-green);
  font-weight: bold;
  margin-right: 0.75rem;
}

.package-cta {
  display: block;
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  padding: 1rem;
  border-radius: 8px;
  text-decoration: none;
  text-align: center;
  font-weight: 600;
  transition: transform 0.3s ease;
}

.package-cta:hover {
  transform: translateY(-2px);
}

/* Why Choose Us */
.why-choose-us {
  padding: 5rem 0;
  background: var(--off-white);
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

  .pricing-grid {
    grid-template-columns: 1fr;
  }

  .pricing-card.popular {
    transform: none;
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
  .pricing-card,
  .benefit-item {
    padding: 1.5rem;
  }
}
</style>
