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
    name: 'Shivam Bhatt',
    company: 'Local Bakery Owner',
    content:
      'AvertoSites delivered exactly what I needed - a beautiful, fast website that brings in customers. The process was smooth and the results exceeded my expectations!',
    rating: 5,
  },
  {
    name: 'Osita Godsend',
    company: 'Restaurant Manager',
    content:
      'Professional, responsive, and affordable. My new website looks amazing and loads lightning fast. Highly recommend!',
    rating: 5,
  },
  {
    name: 'Ahmed Olaleye',
    company: 'De Gentlesoul Global Resources Founder',
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
              Elevate Your Business with AvertoSites<br />
              <span class="highlight">Fast. Affordable. Done Right.</span>
            </h1>
            <p class="hero-description">
              At AvertoSites, we specialize in creating high-performance, visually compelling
              websites that turn visitors into loyal customers. Our expertly crafted websites are
              designed to stand out, load fast, and deliver results. Whether you're launching a new
              site or need ongoing support, we're here to build and maintain a digital presence that
              drives growth.
            </p>

            <div class="special-offer">
              <div class="offer-badge">🎉 LIMITED TIME OFFER</div>
              <h3>Choose Your FREE Bonus: Maintenance OR Domain Registration</h3>
              <p>
                Every new website comes with your choice: 3 months of complimentary maintenance OR
                free domain registration. Pick what works best for your business!
              </p>
            </div>

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
  background: linear-gradient(135deg, var(--logo-blue) 0%, var(--logo-black) 100%);
  color: white;
  padding: 8rem 0;
  min-height: 90vh;
  display: flex;
  align-items: center;
}

.hero-content {
  display: grid;
  grid-template-columns: 1.2fr 0.8fr;
  gap: 5rem;
  align-items: center;
}

.hero-title {
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 700;
  line-height: 1.1;
  margin-bottom: 2rem;
  letter-spacing: -0.02em;
}

.highlight {
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: inline-block;
  margin-top: 1.5rem;
}

.hero-description {
  font-size: clamp(1.1rem, 2vw, 1.3rem);
  line-height: 1.7;
  margin-bottom: 3rem;
  color: var(--light-gray);
  max-width: 600px;
  font-weight: 400;
}

.special-offer {
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
  border: 2px solid rgba(255, 255, 255, 0.2);
  padding: 1.5rem;
  border-radius: 12px;
  margin-bottom: 2rem;
  backdrop-filter: blur(10px);
  position: relative;
  overflow: hidden;
}

.special-offer::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 3px;
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
}

.offer-badge {
  background: linear-gradient(45deg, var(--logo-green), #059669);
  color: white;
  padding: 0.5rem 1rem;
  border-radius: 20px;
  font-size: 0.875rem;
  font-weight: 600;
  display: inline-block;
  margin-bottom: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.special-offer h3 {
  color: white;
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
  font-weight: 600;
}

.special-offer p {
  color: var(--light-gray);
  font-size: 1rem;
  line-height: 1.5;
  margin: 0;
}

.hero-actions {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  align-items: center;
}

.cta-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 1.25rem 2.5rem;
  border-radius: 12px;
  text-decoration: none;
  font-weight: 600;
  font-size: 1.1rem;
  transition: all 0.3s ease;
  border: 2px solid transparent;
  min-height: 56px;
  white-space: nowrap;
}

.cta-button.primary {
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  box-shadow: 0 8px 25px rgba(30, 64, 175, 0.3);
}

.cta-button.primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 35px rgba(30, 64, 175, 0.4);
}

.cta-button.secondary {
  background: transparent;
  color: white;
  border-color: rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(10px);
}

.cta-button.secondary:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: white;
  transform: translateY(-2px);
}

.cta-button.large {
  padding: 1.5rem 3rem;
  font-size: 1.2rem;
}

/* Website Preview Mockup */
.website-preview {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.browser-mockup {
  background: white;
  border-radius: 16px;
  box-shadow: 0 25px 50px rgba(0, 0, 0, 0.25);
  overflow: hidden;
  width: 100%;
  max-width: 550px;
  transform: perspective(1000px) rotateY(-5deg) rotateX(5deg);
  transition: transform 0.3s ease;
}

.browser-mockup:hover {
  transform: perspective(1000px) rotateY(-2deg) rotateX(2deg);
}

.browser-header {
  background: #f8fafc;
  padding: 1.25rem;
  border-bottom: 1px solid #e2e8f0;
  display: flex;
  align-items: center;
}

.browser-dots {
  display: flex;
  gap: 0.75rem;
}

.browser-dots span {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #cbd5e1;
  transition: all 0.3s ease;
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
  padding: 2.5rem;
  background: white;
}

.mockup-content {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

.mockup-header {
  height: 70px;
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  border-radius: 12px;
  box-shadow: 0 4px 12px rgba(30, 64, 175, 0.2);
}

.mockup-hero {
  height: 220px;
  background: linear-gradient(135deg, var(--off-white), var(--light-gray));
  border-radius: 12px;
  position: relative;
  overflow: hidden;
}

.mockup-hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    45deg,
    transparent 30%,
    rgba(255, 255, 255, 0.3) 50%,
    transparent 70%
  );
  animation: shimmer 2s infinite;
}

@keyframes shimmer {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(100%);
  }
}

.mockup-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1.25rem;
}

.mockup-card {
  height: 120px;
  background: var(--off-white);
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.mockup-card:hover {
  transform: translateY(-2px);
}

/* Features Section */
.features {
  padding: 5rem 0;
  background: var(--off-white);
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
  color: var(--logo-black);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.feature-card p {
  color: var(--gray);
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
  color: var(--logo-black);
  margin-bottom: 1rem;
}

.section-header p {
  font-size: 1.1rem;
  color: var(--gray);
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
  background: var(--off-white);
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
  color: var(--logo-green);
  font-size: 0.875rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.portfolio-content h3 {
  color: var(--logo-black);
  margin: 0.5rem 0;
  font-size: 1.25rem;
}

.portfolio-content p {
  color: var(--gray);
  line-height: 1.6;
}

.section-actions {
  text-align: center;
  margin-top: 2rem;
}

.cta-button.secondary {
  background: var(--logo-green);
  color: #fff;
  border: none;
  font-weight: 600;
  box-shadow: 0 2px 8px rgba(5, 150, 105, 0.08);
}

.cta-button.secondary:hover {
  background: var(--green-light);
  color: #fff;
}

/* Testimonials */
.testimonials {
  padding: 5rem 0;
  background: var(--off-white);
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
  color: var(--dark-gray);
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
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
}

.author-info h4 {
  color: var(--logo-black);
  margin-bottom: 0.25rem;
}

.author-info p {
  color: var(--gray);
  font-size: 0.875rem;
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

/* Responsive Design */
@media (max-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 4rem;
    text-align: center;
  }

  .hero-description {
    max-width: 100%;
  }

  .hero-actions {
    justify-content: center;
  }

  .browser-mockup {
    transform: none;
    max-width: 450px;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 6rem 0;
    min-height: auto;
  }

  .hero-title {
    font-size: 2.5rem;
  }

  .hero-description {
    font-size: 1.1rem;
  }

  .special-offer {
    padding: 1.25rem;
  }

  .special-offer h3 {
    font-size: 1.1rem;
  }

  .hero-actions {
    flex-direction: column;
    gap: 1rem;
  }

  .cta-button {
    width: 100%;
    max-width: 300px;
  }

  .browser-mockup {
    max-width: 350px;
  }

  .browser-content {
    padding: 1.5rem;
  }

  .mockup-cards {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
