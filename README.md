# AvertoSites - Professional Web Design & Development

A modern, responsive website for AvertoSites, a professional web design and development business. Built with Vue.js 3, Vite, and modern web technologies.

## 🚀 Features

### Design & User Experience

- **Modern, Professional Design** - Clean, tech-savvy design with deep blue and teal color scheme
- **Fully Responsive** - Optimized for desktop, tablet, and mobile devices
- **Fast Loading** - Built with performance in mind using Vite and modern optimization techniques
- **Accessibility Compliant** - WCAG guidelines followed for inclusive design
- **SEO Optimized** - Meta tags, structured data, and semantic HTML

### Pages & Sections

- **Homepage** - Hero section, features, portfolio preview, testimonials
- **About Us** - Company mission, team bios, values, and process
- **Services** - Comprehensive service offerings with pricing packages
- **Portfolio** - Showcase of recent projects with client testimonials
- **Contact** - Contact form, business information, and FAQ section

### Technical Features

- **Vue.js 3 Composition API** - Modern reactive framework
- **Vue Router** - Client-side routing with lazy loading
- **Vite** - Fast build tool and development server
- **CSS Grid & Flexbox** - Modern layout techniques
- **Mobile-First Design** - Responsive design approach
- **Form Handling** - Contact form with validation
- **Performance Optimized** - Code splitting and lazy loading

## 🛠️ Technology Stack

- **Frontend Framework**: Vue.js 3
- **Build Tool**: Vite
- **Routing**: Vue Router 4
- **Styling**: CSS3 with Grid/Flexbox
- **Fonts**: Inter (Google Fonts)
- **Icons**: Emoji icons and custom CSS
- **Deployment**: Static site hosting ready

## 📦 Installation & Setup

### Prerequisites

- Node.js (version 16 or higher)
- npm or yarn package manager

### Installation Steps

1. **Clone the repository**

   ```bash
   git clone https://github.com/yourusername/avertosites.git
   cd avertosites
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Start development server**

   ```bash
   npm run dev
   ```

4. **Open in browser**
   Navigate to `http://localhost:5173` to view the website

### Build for Production

```bash
npm run build
```

The built files will be in the `dist` directory, ready for deployment.

### Preview Production Build

```bash
npm run preview
```

## 📁 Project Structure

```
avertosites/
├── public/                 # Static assets
│   └── favicon.ico        # Website favicon
├── src/
│   ├── assets/            # Global styles and assets
│   │   ├── base.css       # Base CSS reset
│   │   └── main.css       # Global styles
│   ├── components/        # Vue components
│   ├── router/            # Vue Router configuration
│   │   └── index.js       # Route definitions
│   ├── stores/            # Pinia stores (if needed)
│   ├── views/             # Page components
│   │   ├── HomeView.vue   # Homepage
│   │   ├── AboutView.vue  # About page
│   │   ├── ServicesView.vue # Services page
│   │   ├── PortfolioView.vue # Portfolio page
│   │   └── ContactView.vue # Contact page
│   ├── App.vue            # Root component
│   └── main.js            # Application entry point
├── index.html             # HTML template
├── package.json           # Dependencies and scripts
├── vite.config.js         # Vite configuration
└── README.md              # Project documentation
```

## 🎨 Design System

### Color Palette

- **Primary Blue**: `#06b6d4` (Teal)
- **Secondary Blue**: `#3b82f6` (Blue)
- **Dark Blue**: `#1e3a8a` (Deep Blue)
- **Dark Gray**: `#0f172a` (Navy)
- **Light Gray**: `#f8fafc` (Background)
- **Text Gray**: `#64748b` (Muted text)

### Typography

- **Primary Font**: Inter (Google Fonts)
- **Font Weights**: 300, 400, 500, 600, 700, 800
- **Responsive Typography**: Scales appropriately on different screen sizes

### Brand Elements

- **Slogan**: "FAST • AFFORDABLE • DONE RIGHT"
- **Tagline**: "Custom Websites. Fast. Affordable. Done Right."
- **Brand Voice**: Professional, approachable, trustworthy

## 📱 Responsive Breakpoints

- **Mobile**: < 480px
- **Tablet**: 480px - 768px
- **Desktop**: > 768px

## 🔧 Customization

### Updating Content

- **Text Content**: Edit the respective `.vue` files in the `src/views/` directory
- **Images**: Replace placeholder images in the `public/` directory
- **Colors**: Update CSS custom properties in `src/assets/main.css`
- **Contact Information**: Update contact details in `src/views/ContactView.vue`

### Adding New Pages

1. Create a new `.vue` file in `src/views/`
2. Add the route in `src/router/index.js`
3. Add navigation link in `src/App.vue`

### Styling Changes

- **Global Styles**: Edit `src/assets/main.css`
- **Component Styles**: Edit the `<style>` section in respective `.vue` files
- **Responsive Design**: Use the provided breakpoint classes and media queries

## 📧 Contact Information

- **Email**: contact.avertosites@gmail.com
- **Phone**: +1 (753) 886-1887, +1 (647) 509-8275
- **Business Hours**: Mon-Fri 9AM-6PM EST

## 🚀 Deployment

### Static Hosting (Recommended)

The project builds to static files that can be deployed to any static hosting service:

- **Netlify**: Drag and drop the `dist` folder
- **Vercel**: Connect your GitHub repository
- **GitHub Pages**: Use GitHub Actions for automatic deployment
- **AWS S3**: Upload the `dist` folder to an S3 bucket

### Environment Variables

Create a `.env` file for any environment-specific configurations:

```env
VITE_APP_TITLE=AvertoSites
VITE_APP_DESCRIPTION=Custom Websites. Fast. Affordable. Done Right.
```

## 📈 Performance Optimization

- **Code Splitting**: Routes are lazy-loaded for faster initial load
- **Image Optimization**: Use WebP format and appropriate sizing
- **Font Loading**: Google Fonts are preconnected for faster loading
- **CSS Optimization**: Unused CSS is automatically removed in production
- **Bundle Analysis**: Use `npm run build` to analyze bundle size

## 🔒 Security Considerations

- **Content Security Policy**: Implement CSP headers in production
- **HTTPS**: Always use HTTPS in production
- **Form Validation**: Client-side validation implemented
- **XSS Protection**: Vue.js provides built-in XSS protection

## 📊 Analytics & SEO

### SEO Features

- **Meta Tags**: Comprehensive meta tags for all pages
- **Structured Data**: JSON-LD schema markup
- **Sitemap**: Generate sitemap for better indexing
- **Open Graph**: Social media sharing optimization

### Analytics Integration

Add your analytics tracking code to `index.html`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || []
  function gtag() {
    dataLayer.push(arguments)
  }
  gtag('js', new Date())
  gtag('config', 'GA_MEASUREMENT_ID')
</script>
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Vue.js Team** - For the amazing framework
- **Vite Team** - For the fast build tool
- **Google Fonts** - For the Inter font family
- **Design Inspiration** - Modern web design trends and best practices

---

**Built with ❤️ by AvertoSites**

_Custom Websites. Fast. Affordable. Done Right._
