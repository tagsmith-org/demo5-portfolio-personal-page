# Personal Portfolio - Vue 3 + Tailwind CSS

A clean and minimalist personal portfolio website built with Vue 3, TypeScript, and Tailwind CSS. Features smooth animations, responsive design, and modern UI components.

## 🎨 Design Features

- **Neutral & Elegant Theme**: Background (#F9FAFB), Text (#111827), Accent (#3B82F6)
- **Typography**: Poppins font family from Google Fonts
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Smooth Animations**: Fade-in effects and hover transitions
- **Modern UI**: Clean cards, shadows, and rounded corners

## 🚀 Features

### Sections
1. **Hero Section**: Profile photo, name, profession, and call-to-action buttons
2. **Portfolio Section**: Grid layout with 6 project cards featuring hover zoom effects
3. **Skills Section**: Icon-based skill display with progress indicators
4. **Testimonials Section**: Client feedback with star ratings
5. **Contact Section**: Functional contact form with validation

### Technical Features
- Vue 3 Composition API with TypeScript
- Tailwind CSS for styling
- Responsive grid layouts
- Smooth scroll behavior
- Form validation and submission handling
- Unsplash images for visual content
- Custom animations and transitions

## 🛠️ Tech Stack

- **Frontend**: Vue 3 + TypeScript
- **Styling**: Tailwind CSS
- **Build Tool**: Vite
- **Icons**: Heroicons
- **Images**: Unsplash API

## 📦 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd demo-portfolio-personal-page
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
   Navigate to `http://localhost:3000`

## 🏗️ Build for Production

```bash
npm run build
```

## 📁 Project Structure

```
src/
├── components/
│   ├── HeroSection.vue
│   ├── PortfolioSection.vue
│   ├── SkillsSection.vue
│   ├── TestimonialsSection.vue
│   └── ContactSection.vue
├── App.vue
├── main.ts
└── style.css
```

## 🎯 Customization

### Colors
Update the color scheme in `tailwind.config.js`:
```javascript
colors: {
  background: '#F9FAFB',
  text: '#111827',
  accent: '#3B82F6',
}
```

### Content
- Update personal information in `HeroSection.vue`
- Modify portfolio projects in `PortfolioSection.vue`
- Adjust skills and levels in `SkillsSection.vue`
- Replace testimonials in `TestimonialsSection.vue`
- Update contact information in `ContactSection.vue`

### Images
Replace Unsplash image URLs with your own images or different Unsplash photos.

## 📱 Responsive Design

The portfolio is fully responsive with breakpoints:
- Mobile: `< 768px`
- Tablet: `768px - 1024px`
- Desktop: `> 1024px`

## 🎨 Animations

- **Fade-in animations** for section headers
- **Staggered animations** for portfolio items
- **Hover zoom effects** on project cards
- **Smooth transitions** on interactive elements

## 📧 Contact Form

The contact form includes:
- Form validation
- Loading states
- Success feedback
- Form reset after submission

## 🔧 Development

### Available Scripts
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build

### TypeScript
The project uses TypeScript for type safety. All components include proper interfaces and type definitions.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
