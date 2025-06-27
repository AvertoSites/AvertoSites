<script setup>
import { RouterLink } from 'vue-router'

const features = [
  {
    icon: '⚡',
    title: 'Fast Turnaround',
    description: 'Get your website up and running in days, not weeks.',
  },
  {
    icon: '🔍',
    title: 'SEO Optimized',
    description: 'Built for search engines to help you rank higher.',
  },
  {
    icon: '📱',
    title: 'Mobile Friendly',
    description: 'Perfect on all devices - desktop, tablet, and mobile.',
  },
  {
    icon: '💰',
    title: 'Affordable Pricing',
    description: 'Professional quality at prices that work for your budget.',
  },
]

const portfolioItems = [
  {
    title: 'DE Gentlesoul Resources',
    category: 'Travel Agency',
    image: '/gentlesoul.png',
    description:
      'De Gentlesoul Global Resources is a professional travel and education consulting agency that specializes in visa applications, school admissions, hotel accommodations, and flight bookings, offering hassle-free services with the motto "We do the stressing while you do the flexing" to help clients achieve their international travel and study abroad goals.',
  },
  // {
  //   title: 'Restaurant Website',
  //   category: 'Food & Beverage',
  //   image: '/api/placeholder/400/300',
  //   description: 'Elegant website with online ordering system',
  // },
  // {
  //   title: 'Consulting Firm',
  //   category: 'Professional Services',
  //   image: '/api/placeholder/400/300',
  //   description: 'Professional website with lead generation',
  // },
]

const testimonials = [
  {
    name: 'Sarah Johnson',
    company: 'Local Bakery Owner',
    content:
      'AvertoSites delivered exactly what I needed - a beautiful, fast website that brings in customers. The process was smooth and the results exceeded my expectations!',
    rating: 5,
  },
  {
    name: 'Mike Chen',
    company: 'Tech Startup Founder',
    content:
      'Professional, responsive, and affordable. My new website looks amazing and loads lightning fast. Highly recommend!',
    rating: 5,
  },
  {
    name: 'Emily Rodriguez',
    company: 'Fitness Coach',
    content:
      'The team at AvertoSites understood my vision perfectly. My website now reflects my brand and helps me connect with clients effectively.',
    rating: 5,
  },
]
</script>

<template>
  <div class="home">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <div class="hero-text">
            <h1 class="hero-title">
              Custom Websites.<br />
              <span class="highlight">Fast. Affordable. Done Right.</span>
            </h1>
            <p class="hero-description">
              Transform your business with a professional website that converts visitors into
              customers. We create stunning, fast-loading websites that help you stand out online.
            </p>
            <div class="hero-actions">
              <RouterLink to="/contact" class="cta-button primary"
                >Start Your Website Today</RouterLink
              >
              <RouterLink to="/portfolio" class="cta-button secondary">View Our Work</RouterLink>
            </div>
          </div>
          <div class="hero-visual">
            <div class="website-preview">
              <div class="browser-mockup">
                <div class="browser-header">
                  <div class="browser-dots">
                    <span></span>
                    <span></span>
                    <span></span>
                  </div>
                </div>
                <div class="browser-content">
                  <div class="mockup-content">
                    <div class="mockup-header"></div>
                    <div class="mockup-hero"></div>
                    <div class="mockup-cards">
                      <div class="mockup-card"></div>
                      <div class="mockup-card"></div>
                      <div class="mockup-card"></div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Features Section -->
    <section class="features">
      <div class="container">
        <div class="features-grid">
          <div v-for="feature in features" :key="feature.title" class="feature-card">
            <div class="feature-icon">{{ feature.icon }}</div>
            <h3>{{ feature.title }}</h3>
            <p>{{ feature.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Portfolio Preview -->
    <section class="portfolio-preview">
      <div class="container">
        <div class="section-header">
          <h2>Recent Work</h2>
          <p>See how we've helped businesses like yours succeed online</p>
        </div>
        <div class="portfolio-grid">
          <div v-for="item in portfolioItems" :key="item.title" class="portfolio-item">
            <div class="portfolio-image">
              <div class="placeholder-image"><img :src="item.image" alt="" /></div>
            </div>
            <div class="portfolio-content">
              <span class="portfolio-category">{{ item.category }}</span>
              <h3>{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>
          </div>
        </div>
        <div class="section-actions">
          <RouterLink to="/portfolio" class="cta-button secondary">View More Projects</RouterLink>
        </div>
      </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials">
      <div class="container">
        <div class="section-header">
          <h2>What Our Clients Say</h2>
          <p>Don't just take our word for it - hear from our satisfied clients</p>
        </div>
        <div class="testimonials-grid">
          <div v-for="testimonial in testimonials" :key="testimonial.name" class="testimonial-card">
            <div class="testimonial-rating">
              <span v-for="i in testimonial.rating" :key="i" class="star">⭐</span>
            </div>
            <p class="testimonial-content">"{{ testimonial.content }}"</p>
            <div class="testimonial-author">
              <div class="author-avatar"></div>
              <div class="author-info">
                <h4>{{ testimonial.name }}</h4>
                <p>{{ testimonial.company }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="cta-section">
      <div class="container">
        <div class="cta-content">
          <h2>Ready to Launch Your Website?</h2>
          <p>Let's create something amazing together. Get started with a free consultation.</p>
          <RouterLink to="/contact" class="cta-button primary large">Start Your Project</RouterLink>
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
  padding: 6rem 0;
  min-height: 80vh;
  display: flex;
  align-items: center;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 1.5rem;
}

.highlight {
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-description {
  font-size: 1.25rem;
  line-height: 1.6;
  margin-bottom: 2rem;
  color: #cbd5e1;
}

.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.cta-button {
  display: inline-block;
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.cta-button.primary {
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  color: white;
}

.cta-button.primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 25px rgba(6, 182, 212, 0.3);
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

.cta-button.large {
  padding: 1.25rem 2.5rem;
  font-size: 1.1rem;
}

/* Website Preview Mockup */
.website-preview {
  display: flex;
  justify-content: center;
  align-items: center;
}

.browser-mockup {
  background: white;
  border-radius: 12px;
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
  overflow: hidden;
  width: 100%;
  max-width: 500px;
}

.browser-header {
  background: #f1f5f9;
  padding: 1rem;
  border-bottom: 1px solid #e2e8f0;
}

.browser-dots {
  display: flex;
  gap: 0.5rem;
}

.browser-dots span {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #cbd5e1;
}

.browser-dots span:nth-child(1) {
  background: #ef4444;
}
.browser-dots span:nth-child(2) {
  background: #f59e0b;
}
.browser-dots span:nth-child(3) {
  background: #10b981;
}

.browser-content {
  padding: 2rem;
  background: white;
}

.mockup-content {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.mockup-header {
  height: 60px;
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  border-radius: 8px;
}

.mockup-hero {
  height: 200px;
  background: linear-gradient(45deg, #f8fafc, #e2e8f0);
  border-radius: 8px;
}

.mockup-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.mockup-card {
  height: 100px;
  background: #f1f5f9;
  border-radius: 8px;
}

/* Features Section */
.features {
  padding: 5rem 0;
  background: #f8fafc;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.feature-card h3 {
  color: #1e293b;
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.feature-card p {
  color: #64748b;
  line-height: 1.6;
}

/* Portfolio Preview */
.portfolio-preview {
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
}

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.portfolio-item {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
  display: flex;
  flex-direction: column;
}

.portfolio-item:hover {
  transform: translateY(-5px);
}

.portfolio-image {
  width: 100%;
  height: 200px;
  background: #f1f5f9;
  display: flex;
  align-items: center;
  justify-content: center;
}

.placeholder-image {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.placeholder-image img {
  max-width: 100%;
  max-height: 180px;
  object-fit: contain;
  display: block;
  margin: 0 auto;
}

.portfolio-content {
  padding: 1.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}

.portfolio-category {
  color: #06b6d4;
  font-size: 0.875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.portfolio-content h3 {
  color: #1e293b;
  margin: 0.5rem 0;
  font-size: 1.25rem;
}

.portfolio-content p {
  color: #64748b;
  line-height: 1.6;
}

.section-actions {
  text-align: center;
  margin-top: 2rem;
}

.cta-button.secondary {
  background: #06b6d4;
  color: #fff;
  border: none;
  font-weight: 600;
  box-shadow: 0 2px 8px rgba(6, 182, 212, 0.08);
}

.cta-button.secondary:hover {
  background: #3b82f6;
  color: #fff;
}

/* Testimonials */
.testimonials {
  padding: 5rem 0;
  background: #f8fafc;
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.testimonial-card {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.testimonial-rating {
  margin-bottom: 1rem;
}

.star {
  margin-right: 0.25rem;
}

.testimonial-content {
  font-style: italic;
  color: #374151;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.testimonial-author {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.author-avatar {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
}

.author-info h4 {
  color: #1e293b;
  margin-bottom: 0.25rem;
}

.author-info p {
  color: #64748b;
  font-size: 0.875rem;
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

/* Responsive Design */
@media (max-width: 768px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 2rem;
    text-align: center;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-actions {
    justify-content: center;
  }

  .features-grid {
    grid-template-columns: 1fr;
  }

  .portfolio-grid {
    grid-template-columns: 1fr;
  }

  .testimonials-grid {
    grid-template-columns: 1fr;
  }

  .section-header h2 {
    font-size: 2rem;
  }

  .cta-content h2 {
    font-size: 2rem;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 4rem 0;
  }

  .hero-title {
    font-size: 2rem;
  }

  .hero-actions {
    flex-direction: column;
    align-items: center;
  }

  .cta-button {
    width: 100%;
    text-align: center;
  }
}
</style>
