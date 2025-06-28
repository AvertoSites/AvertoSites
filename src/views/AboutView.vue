<script setup>
import { RouterLink } from 'vue-router'

const teamMembers = [
  {
    name: 'Abdul-muiz Olaleye',
    image: '/muiz.jpg',
    link: 'http://www.abdulmuizolaleye.com/',
    role: 'Co-Founder & Lead Developer',
    bio: 'Passionate about creating websites that not only look great but drive real business results. Specializes in modern web technologies.',
    focus: 'Website Design & Development',
  },
  {
    name: 'Somtochukwu Kay-Okerulu',
    image: '/somto.jpg',
    link: 'https://www.linkedin.com/in/somtochukwu-k-32b5bb28b?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app',
    role: 'Co-Founder & Brand Strategist',
    bio: 'Expert in social media marketing and brand development. Helps businesses create compelling online presence and engage with their audience effectively.',
    focus: 'Social Media + Branding',
  },
]

const values = [
  {
    icon: '🎯',
    title: 'Results-Driven',
    description: 'We focus on creating websites that convert visitors into loyal customers.',
  },
  {
    icon: '⚡',
    title: 'Fast Delivery',
    description: 'Quick turnaround times without compromising on quality.',
  },
  {
    icon: '🤝',
    title: 'Client Partnership',
    description: 'We work closely with you to ensure your vision becomes reality.',
  },
  {
    icon: '💡',
    title: 'Innovation',
    description: 'Always staying ahead with the latest web technologies and trends.',
  },
]
</script>

<template>
  <div class="about">
    <!-- Hero Section -->
    <section class="hero">
      <div class="container">
        <div class="hero-content">
          <h1>About AvertoSites</h1>
          <p class="hero-subtitle">We're passionate about helping businesses succeed online</p>
        </div>
      </div>
    </section>

    <!-- Mission Section -->
    <section class="mission">
      <div class="container">
        <div class="mission-content">
          <div class="mission-text">
            <h2>Our Mission</h2>
            <p class="mission-statement">
              At AvertoSites, we believe every business deserves a professional, conversion-ready
              website that helps them stand out online. Our mission is to make high-quality web
              design accessible and affordable for entrepreneurs, small businesses, and individuals
              who want to make their mark on the digital world.
            </p>
            <p class="mission-statement">
              We're not just building websites – we're creating digital experiences that drive
              results. Whether you're launching a new business, expanding your online presence, or
              looking to modernize your current site, we're here to help you succeed.
            </p>
            <div class="slogan-display">
              <span class="slogan-item">FAST</span>
              <span class="slogan-item">AFFORDABLE</span>
              <span class="slogan-item">DONE RIGHT</span>
            </div>
          </div>
          <div class="mission-visual">
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
                <div class="stat-number">7</div>
                <div class="stat-label">Days Average</div>
              </div>
              <div class="stat-item">
                <div class="stat-number">24/7</div>
                <div class="stat-label">Support Available</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Team Section -->
    <section class="team">
      <div class="container">
        <div class="section-header">
          <h2>Meet Our Team</h2>
          <p>
            Small team, big impact. We're dedicated to delivering exceptional results for every
            client.
          </p>
        </div>
        <div class="team-grid">
          <div v-for="member in teamMembers" :key="member.name" class="team-member">
            <div class="member-card">
              <div class="member-avatar">
                <img :src="member.image" :alt="member.name" />
                <div class="avatar-overlay">
                  <a :href="member.link" target="_blank" rel="noopener" class="profile-link">
                    <span>View Profile</span>
                  </a>
                </div>
              </div>
              <div class="member-info">
                <h3>{{ member.name }}</h3>
                <p class="member-role">{{ member.role }}</p>
                <div class="member-focus">
                  <span class="focus-label">Focus:</span>
                  <span class="focus-area">{{ member.focus }}</span>
                </div>
                <p class="member-bio">{{ member.bio }}</p>
                <div class="member-social">
                  <a :href="member.link" target="_blank" rel="noopener" class="social-link">
                    <span>Connect</span>
                    <svg
                      width="16"
                      height="16"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="2"
                    >
                      <path d="M7 17L17 7M17 7H7M17 7V17" />
                    </svg>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Values Section -->
    <section class="values">
      <div class="container">
        <div class="section-header">
          <h2>Our Values</h2>
          <p>The principles that guide everything we do</p>
        </div>
        <div class="values-grid">
          <div v-for="value in values" :key="value.title" class="value-card">
            <div class="value-icon">{{ value.icon }}</div>
            <h3>{{ value.title }}</h3>
            <p>{{ value.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Process Section -->
    <section class="process">
      <div class="container">
        <div class="section-header">
          <h2>How We Work</h2>
          <p>
            Our streamlined process ensures your project is completed efficiently and exceeds
            expectations
          </p>
        </div>
        <div class="process-steps">
          <div class="process-step">
            <div class="step-number">1</div>
            <h3>Discovery</h3>
            <p>We start by understanding your business, goals, and vision for your website.</p>
          </div>
          <div class="process-step">
            <div class="step-number">2</div>
            <h3>Design</h3>
            <p>
              We create a custom design that reflects your brand and appeals to your target
              audience.
            </p>
          </div>
          <div class="process-step">
            <div class="step-number">3</div>
            <h3>Development</h3>
            <p>
              We build your website using modern technologies for speed, security, and performance.
            </p>
          </div>
          <div class="process-step">
            <div class="step-number">4</div>
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
          <h2>Ready to Work Together?</h2>
          <p>Let's discuss your project and see how we can help bring your vision to life.</p>
          <RouterLink to="/contact" class="cta-button">Start Your Project</RouterLink>
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

/* Mission Section */
.mission {
  padding: 5rem 0;
  background: var(--off-white);
}

.mission-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: center;
}

.mission-text h2 {
  font-size: 2.5rem;
  color: var(--logo-black);
  margin-bottom: 2rem;
}

.mission-statement {
  font-size: 1.1rem;
  line-height: 1.7;
  color: var(--dark-gray);
  margin-bottom: 1.5rem;
}

.slogan-display {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
  flex-wrap: wrap;
}

.slogan-item {
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  font-weight: 600;
  font-size: 0.9rem;
  letter-spacing: 0.5px;
}

/* Stats Grid */
.stats-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 2rem;
}

.stat-item {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  text-align: center;
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

/* Team Section */
.team {
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

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  max-width: 1000px;
  margin: 0 auto;
}

.team-member {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
}

.team-member:hover {
  transform: translateY(-8px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.15);
}

.member-card {
  position: relative;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.member-avatar {
  position: relative;
  width: 100%;
  height: 320px;
  overflow: hidden;
}

.member-avatar img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.team-member:hover .member-avatar img {
  transform: scale(1.05);
}

.avatar-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(30, 64, 175, 0.8), rgba(5, 150, 105, 0.8));
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.avatar-overlay:hover {
  opacity: 1;
}

.profile-link {
  text-decoration: none;
  color: white;
  padding: 0.75rem 1.5rem;
  border: 2px solid white;
  border-radius: 25px;
  font-weight: 600;
  font-size: 0.9rem;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
}

.profile-link:hover {
  background: white;
  color: var(--logo-blue);
}

.member-info {
  padding: 2rem;
  text-align: center;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.member-info h3 {
  color: var(--logo-black);
  margin-bottom: 0.5rem;
  font-size: 1.5rem;
  font-weight: 700;
}

.member-role {
  color: var(--logo-blue);
  font-weight: 600;
  margin-bottom: 1rem;
  font-size: 1.1rem;
}

.member-focus {
  margin-bottom: 1.5rem;
  padding: 0.75rem 1rem;
  background: var(--off-white);
  border-radius: 8px;
  border-left: 4px solid var(--logo-green);
}

.focus-label {
  color: var(--gray);
  font-size: 0.9rem;
  font-weight: 500;
}

.focus-area {
  color: var(--logo-black);
  font-weight: 600;
  margin-left: 0.5rem;
}

.member-bio {
  color: var(--gray);
  line-height: 1.6;
  margin-bottom: 1.5rem;
  flex: 1;
}

.member-social {
  margin-top: auto;
}

.social-link {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  color: var(--logo-blue);
  padding: 0.75rem 1.5rem;
  border: 2px solid var(--logo-blue);
  border-radius: 25px;
  font-weight: 600;
  font-size: 0.9rem;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
}

.social-link:hover {
  background: var(--logo-blue);
  color: white;
  transform: translateY(-2px);
}

.social-link svg {
  transition: transform 0.3s ease;
}

.social-link:hover svg {
  transform: translateX(2px);
}

/* Values Section */
.values {
  padding: 5rem 0;
  background: var(--off-white);
}

.values-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.value-card {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  text-align: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: transform 0.3s ease;
}

.value-card:hover {
  transform: translateY(-5px);
}

.value-icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.value-card h3 {
  color: var(--logo-black);
  margin-bottom: 1rem;
  font-size: 1.25rem;
}

.value-card p {
  color: var(--gray);
  line-height: 1.6;
}

/* Process Section */
.process {
  padding: 5rem 0;
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
  margin: 0 auto 1.5rem;
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

.cta-button {
  display: inline-block;
  background: linear-gradient(45deg, var(--logo-blue), var(--logo-green));
  color: white;
  padding: 1rem 2rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  transition: transform 0.3s ease;
}

.cta-button:hover {
  transform: translateY(-2px);
}

/* Responsive Design */
@media (max-width: 768px) {
  .mission-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }

  .team-grid {
    grid-template-columns: 1fr;
  }

  .team-member {
    flex-direction: column;
    text-align: center;
  }

  .stats-grid {
    grid-template-columns: 1fr;
  }

  .process-steps {
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
}

@media (max-width: 480px) {
  .hero h1 {
    font-size: 2rem;
  }

  .slogan-display {
    flex-direction: column;
    align-items: center;
  }

  .slogan-item {
    width: fit-content;
  }
}
</style>
