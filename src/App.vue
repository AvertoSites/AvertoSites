<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref, onMounted } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}

onMounted(() => {
  // Close mobile menu when clicking outside
  document.addEventListener('click', (e) => {
    if (!e.target.closest('.nav-container')) {
      isMenuOpen.value = false
    }
  })
})
</script>

<template>
  <div id="app">
    <!-- Header -->
    <header class="header">
      <div class="container">
        <div class="nav-container">
          <RouterLink to="/" class="logo" @click="closeMenu">
            <img
              src="/avertoLogo.png"
              alt="AvertoSites Logo"
              class="logo-img"
              width="48"
              height="48"
              style="vertical-align: middle"
            />
            <span class="logo-text">AvertoSites</span>
          </RouterLink>

          <!-- Mobile menu button -->
          <button class="mobile-menu-btn" @click="toggleMenu" :class="{ active: isMenuOpen }">
            <span></span>
            <span></span>
            <span></span>
          </button>

          <!-- Navigation -->
          <nav class="nav" :class="{ 'nav-open': isMenuOpen }">
            <RouterLink to="/" @click="closeMenu">Home</RouterLink>
            <RouterLink to="/about" @click="closeMenu">About</RouterLink>
            <RouterLink to="/services" @click="closeMenu">Services</RouterLink>
            <RouterLink to="/portfolio" @click="closeMenu">Portfolio</RouterLink>
            <RouterLink to="/contact" @click="closeMenu">Contact</RouterLink>
          </nav>
        </div>
      </div>
    </header>

    <!-- Main Content -->
    <main class="main">
      <RouterView />
    </main>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-section">
            <h3>AvertoSites</h3>
            <p class="slogan">FAST • AFFORDABLE • DONE RIGHT</p>
            <p>Custom websites that convert. Professional design meets powerful functionality.</p>
          </div>

          <div class="footer-section">
            <h4>Services</h4>
            <ul>
              <li><RouterLink to="/services">Website Design</RouterLink></li>
              <li><RouterLink to="/services">SEO Optimization</RouterLink></li>
              <li><RouterLink to="/services">Maintenance</RouterLink></li>
              <li><RouterLink to="/services">Branding</RouterLink></li>
            </ul>
          </div>

          <div class="footer-section">
            <h4>Contact</h4>
            <p>Ready to launch your website?</p>
            <RouterLink to="/contact" class="cta-button">Let's Talk</RouterLink>
            <div class="contact-info">
              <p>📧 contact.avertosites@gmail.com</p>
              <p>📞 +1 (647) 509-8275</p>
              <p>📞 +1 (753) 886-1887</p>
            </div>
          </div>

          <div class="footer-section">
            <h4>Follow Us</h4>
            <div class="social-links">
              <a href="https://www.instagram.com/avertosites?igsh=OGwwNnZlaXR2eHcz&utm_source=qr" target="_blank" rel="noopener">Instagram</a>
              <a href="https://www.tiktok.com/@avertosites" target="_blank" rel="noopener">TikTok</a>
            </div>
          </div>
        </div>

        <div class="footer-bottom">
          <p>&copy; 2025 AvertoSites. All rights reserved.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
/* Reset and base styles */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Header Styles */
.header {
  background: linear-gradient(135deg, #1e3a8a 0%, #0f172a 100%);
  color: white;
  padding: 1rem 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.1);
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  text-decoration: none;
  color: white;
}

.logo-text {
  font-size: 1.8rem;
  font-weight: 700;
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: inline-block;
  vertical-align: middle;
  margin-left: 0.5rem;
}

/* Navigation */
.nav {
  display: flex;
  gap: 2rem;
  align-items: center;
}

.nav a {
  color: white;
  text-decoration: none;
  font-weight: 500;
  transition: color 0.3s ease;
  position: relative;
}

.nav a:hover {
  color: #06b6d4;
}

.nav a.router-link-active {
  color: #06b6d4;
}

.nav a.router-link-active::after {
  content: '';
  position: absolute;
  bottom: -5px;
  left: 0;
  width: 100%;
  height: 2px;
  background: #06b6d4;
}

/* Mobile menu button */
.mobile-menu-btn {
  display: none;
  flex-direction: column;
  background: none;
  border: none;
  cursor: pointer;
  padding: 5px;
}

.mobile-menu-btn span {
  width: 25px;
  height: 3px;
  background: white;
  margin: 3px 0;
  transition: 0.3s;
  border-radius: 2px;
}

.mobile-menu-btn.active span:nth-child(1) {
  transform: rotate(-45deg) translate(-5px, 6px);
}

.mobile-menu-btn.active span:nth-child(2) {
  opacity: 0;
}

.mobile-menu-btn.active span:nth-child(3) {
  transform: rotate(45deg) translate(-5px, -6px);
}

/* Main content */
.main {
  flex: 1;
}

/* Footer */
.footer {
  background: #0f172a;
  color: white;
  padding: 3rem 0 1rem;
  margin-top: auto;
}

.footer-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
  margin-bottom: 2rem;
}

.footer-section h3 {
  color: #06b6d4;
  margin-bottom: 1rem;
  font-size: 1.5rem;
}

.footer-section h4 {
  color: #06b6d4;
  margin-bottom: 1rem;
}

.slogan {
  font-weight: 600;
  color: #3b82f6;
  margin-bottom: 1rem;
  letter-spacing: 1px;
}

.footer-section ul {
  list-style: none;
}

.footer-section ul li {
  margin-bottom: 0.5rem;
}

.footer-section a {
  color: #cbd5e1;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-section a:hover {
  color: #06b6d4;
}

.cta-button {
  display: inline-block;
  background: linear-gradient(45deg, #06b6d4, #3b82f6);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  margin: 1rem 0;
  transition: transform 0.3s ease;
}

.cta-button:hover {
  transform: translateY(-2px);
}

.contact-info p {
  margin: 0.5rem 0;
  color: #cbd5e1;
}

.social-links {
  display: flex;
  gap: 1rem;
}

.social-links a {
  color: #cbd5e1;
  text-decoration: none;
  transition: color 0.3s ease;
}

.social-links a:hover {
  color: #06b6d4;
}

.footer-bottom {
  border-top: 1px solid #334155;
  padding-top: 1rem;
  text-align: center;
  color: #64748b;
}

/* Responsive Design */
@media (max-width: 768px) {
  .mobile-menu-btn {
    display: flex;
  }

  .nav {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background: #0f172a;
    flex-direction: column;
    padding: 2rem;
    gap: 1rem;
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all 0.3s ease;
  }

  .nav.nav-open {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }

  .nav a {
    padding: 0.5rem 0;
    width: 100%;
    text-align: center;
  }

  .footer-content {
    grid-template-columns: 1fr;
    text-align: center;
  }

  .social-links {
    justify-content: center;
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 15px;
  }

  .logo-text {
    font-size: 1.5rem;
  }
}

/* Add visually-hidden class for accessibility */
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

.logo-img {
  display: inline-block;
  height: 48px;
  width: 48px;
  margin-right: 0.5rem;
  vertical-align: middle;
}
</style>
