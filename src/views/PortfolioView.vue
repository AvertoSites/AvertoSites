<script setup>
import { RouterLink } from 'vue-router'

const portfolioItems = [
  {
    title: 'De Gentlesoul Global Resources',
    category: 'Travel & Education Consulting',
    description:
      'A professional travel and education consulting website offering visa applications, school admissions, hotel bookings, and flight arrangements with seamless appointment scheduling.',
    image: '/gentlesoul.png',
    link: 'https://degentlesoulresources.info/',
    features: [
      'Appointment booking system',
      'Service catalog',
      'Mobile responsive',
      'SEO optimized',
      'WhatsApp integration',
      'Calendly integration',
    ],
    client: 'De Gentlesoul Global Resources',

    testimonial:
      'The website perfectly represents our professional services and has significantly improved our client engagement. The booking system has streamlined our appointment process!',
    technologies: ['Vue.js', 'Vite', 'Google Analytics', 'Calendly API', 'WhatsApp API'],
  },
  // {
  //   title: 'TechFlow Solutions',
  //   category: 'Technology',
  //   description: 'Professional consulting firm website with lead generation and client portal.',
  //   image: '/api/placeholder/600/400',
  //   features: ['Lead generation forms', 'Client portal', 'Case studies', 'Blog integration'],
  //   client: 'Mike Chen',
  //   testimonial:
  //     'AvertoSites delivered a website that positions us as industry leaders. Our lead quality has improved significantly.',
  //   technologies: ['React', 'Firebase', 'Mailchimp', 'Google Analytics'],
  // },
  // {
  //   title: 'FitLife Studio',
  //   category: 'Fitness & Health',
  //   description: 'Dynamic fitness studio website with class booking and member management.',
  //   image: '/api/placeholder/600/400',
  //   features: [
  //     'Class booking system',
  //     'Member profiles',
  //     'Payment integration',
  //     'Social media feeds',
  //   ],
  //   client: 'Emily Rodriguez',
  //   testimonial:
  //     'The booking system is so easy to use. Our members love the convenience, and our admin work has been cut in half.',
  //   technologies: ['Vue.js', 'Laravel', 'PayPal API', 'Instagram API'],
  // },
  // {
  //   title: 'GreenScape Landscaping',
  //   category: 'Home Services',
  //   description: 'Landscaping company website with project portfolio and quote request system.',
  //   image: '/api/placeholder/600/400',
  //   features: ['Project gallery', 'Quote calculator', 'Before/after images', 'Service areas'],
  //   client: 'David Thompson',
  //   testimonial:
  //     "The project gallery showcases our work beautifully. We've received more high-quality leads than ever before.",
  //   technologies: ['WordPress', 'PHP', 'MySQL', 'Google Maps API'],
  // },
  // {
  //   title: 'Creative Minds Agency',
  //   category: 'Marketing & Design',
  //   description: 'Creative agency website with portfolio showcase and client testimonials.',
  //   image: '/api/placeholder/600/400',
  //   features: ['Portfolio showcase', 'Client testimonials', 'Service pages', 'Contact forms'],
  //   client: 'Lisa Wang',
  //   testimonial:
  //     "The portfolio section perfectly highlights our creative work. It's become our best sales tool.",
  //   technologies: ['Next.js', 'Sanity CMS', 'Vercel', 'Framer Motion'],
  // },
  // {
  //   title: 'Urban Coffee Co.',
  //   category: 'Retail',
  //   description: 'Coffee shop website with online ordering and loyalty program integration.',
  //   image: '/api/placeholder/600/400',
  //   features: ['Online ordering', 'Loyalty program', 'Menu management', 'Location finder'],
  //   client: 'Alex Martinez',
  //   testimonial:
  //     'The online ordering system has been a game-changer. Our customers love the convenience.',
  //   technologies: ['React', 'Stripe', 'Firebase', 'Google Places API'],
  // },
]

const categories = [
  'All',
  'Travel Agency',
  // 'Food & Beverage',
  // 'Technology',
  // 'Fitness & Health',
  // 'Home Services',
  // 'Marketing & Design',
  // 'Retail',
]
</script>

<template>
  <div class="portfolio">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1>Our Portfolio</h1>
          <p class="hero-subtitle">
            See how we've helped businesses transform their online presence
          </p>
        </div>
      </div>
    </section>

    <!-- Portfolio Filter -->
    <section class="portfolio-filter">
      <div class="container">
        <div class="filter-buttons">
          <button
            v-for="category in categories"
            :key="category"
            class="filter-btn"
            :class="{ active: category === 'All' }"
          >
            {{ category }}
          </button>
        </div>
      </div>
    </section>

    <!-- Portfolio Grid -->
    <section class="portfolio-grid">
      <div class="container">
        <div class="projects-grid">
          <div v-for="item in portfolioItems" :key="item.title" class="project-card">
            <div class="project-image">
              <img :src="item.image" alt="Project Image" class="project-image-img" />
              <div class="project-overlay">
                <a :href="item.link" target="_blank" rel="noopener" class="view-project-btn"
                  >View Project</a
                >
              </div>
            </div>
            <div class="project-content">
              <div class="project-category">{{ item.category }}</div>
              <h3>{{ item.title }}</h3>
              <p class="project-description">{{ item.description }}</p>

              <div class="project-features">
                <h4>Key Features:</h4>
                <ul>
                  <li v-for="feature in item.features" :key="feature">{{ feature }}</li>
                </ul>
              </div>

              <div class="project-technologies">
                <h4>Technologies:</h4>
                <div class="tech-tags">
                  <span v-for="tech in item.technologies" :key="tech" class="tech-tag">{{
                    tech
                  }}</span>
                </div>
              </div>

              <div class="client-testimonial">
                <div class="testimonial-content">
                  <p>"{{ item.testimonial }}"</p>
                  <div class="client-info">
                    <strong>{{ item.client }}</strong>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Statistics Section -->
    <section class="statistics">
      <div class="container">
        <div class="stats-grid">
          <div class="stat-item">
            <div class="stat-number">5+</div>
            <div class="stat-label">Websites Created</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">98%</div>
            <div class="stat-label">Client Satisfaction</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">40%</div>
            <div class="stat-label">Average Traffic Increase</div>
          </div>
          <div class="stat-item">
            <div class="stat-number">7</div>
            <div class="stat-label">Days Average Delivery</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="process">
      <div class="container">
        <div class="section-header">
          <h2>Our Design Process</h2>
          <p>How we bring your vision to life with our proven methodology</p>
        </div>
        <div class="process-steps">
          <div class="process-step">
            <div class="step-icon">🎯</div>
            <h3>Discovery</h3>
            <p>
              We dive deep into understanding your business, goals, and target audience to create
              the perfect strategy.
            </p>
          </div>
          <div class="process-step">
            <div class="step-icon">✏️</div>
            <h3>Design</h3>
            <p>
              We create wireframes and mockups, ensuring every element serves your business
              objectives.
            </p>
          </div>
          <div class="process-step">
            <div class="step-icon">💻</div>
            <h3>Development</h3>
            <p>
              We build your website using modern technologies, ensuring speed, security, and
              performance.
            </p>
          </div>
          <div class="process-step">
            <div class="step-icon">🚀</div>
            <h3>Launch</h3>
            <p>
              We deploy your website and provide training to help you manage and grow your online
              presence.
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Join Our Success Stories?</h2>
          <p>Let's create something amazing together. Your next project could be featured here!</p>
          <div class="cta-actions">
            <RouterLink to="/contact" class="cta-button primary">Start Your Project</RouterLink>
            <RouterLink to="/services" class="cta-button secondary">View Services</RouterLink>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
a {
  cursor: pointer;
}
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

/* Portfolio Filter */
.portfolio-filter {
  padding: 2rem 0;
  background: var(--off-white);
  border-bottom: 1px solid #e2e8f0;
}

.filter-buttons {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.filter-btn {
  background: white;
  border: 2px solid #e2e8f0;
  color: var(--gray);
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 500;
}

.filter-btn:hover,
.filter-btn.active {
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  border-color: transparent;
}

/* Portfolio Grid */
.portfolio-grid {
  padding: 5rem 0;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 3rem;
}

.project-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateY(-5px);
}

.project-image {
  position: relative;
  height: 250px;
  overflow: hidden;
}

.placeholder-image {
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #e2e8f0, #cbd5e1);
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(30, 64, 175, 0.9);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.view-project-btn {
  background: white;
  color: var(--logo-blue);
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: transform 0.3s ease;
}

.view-project-btn:hover {
  transform: scale(1.05);
}

.project-content {
  padding: 2rem;
}

.project-category {
  color: var(--logo-green);
  font-size: 0.875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 0.5rem;
}

.project-content h3 {
  color: var(--logo-black);
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.project-description {
  color: var(--gray);
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.project-features h4,
.project-technologies h4 {
  color: var(--logo-black);
  margin-bottom: 0.5rem;
  font-size: 1rem;
}

.project-features ul {
  list-style: none;
  margin-bottom: 1.5rem;
}

.project-features li {
  color: var(--dark-gray);
  margin-bottom: 0.25rem;
  padding-left: 1rem;
  position: relative;
}

.project-features li::before {
  content: '•';
  position: absolute;
  left: 0;
  color: var(--logo-green);
}

.tech-tags {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tech-tag {
  background: var(--off-white);
  color: var(--dark-gray);
  padding: 0.25rem 0.75rem;
  border-radius: 15px;
  font-size: 0.875rem;
  font-weight: 500;
}

.client-testimonial {
  background: var(--off-white);
  padding: 1.5rem;
  border-radius: 8px;
  border-left: 4px solid var(--logo-green);
}

.testimonial-content p {
  color: var(--dark-gray);
  font-style: italic;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.client-info {
  color: var(--gray);
  font-size: 0.9rem;
}

/* Statistics Section */
.statistics {
  padding: 5rem 0;
  background: var(--off-white);
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 2rem;
}

.stat-item {
  text-align: center;
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.stat-number {
  font-size: 2.5rem;
  font-weight: 700;
  color: var(--logo-blue);
  margin-bottom: 0.5rem;
}

.stat-label {
  color: var(--gray);
  font-weight: 500;
}

/* Process Section */
.process {
  padding: 5rem 0;
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

.process-steps {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.process-step {
  text-align: center;
  padding: 2rem;
}

.step-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.process-step h3 {
  color: var(--logo-black);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.process-step p {
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
  .projects-grid {
    grid-template-columns: 1fr;
  }

  .stats-grid {
    grid-template-columns: repeat(2, 1fr);
  }

  .process-steps {
    grid-template-columns: 1fr;
  }

  .filter-buttons {
    justify-content: flex-start;
    overflow-x: auto;
    padding-bottom: 0.5rem;
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

  .stats-grid {
    grid-template-columns: 1fr;
  }

  .project-card {
    margin: 0 1rem;
  }
}
</style>
