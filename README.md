# KIWi Webpage

**KIWi** („KI & Wissenschaft") ist ein gemeinsames Bildungsprojekt des **Softwarepark Hagenberg (SWPH)**, das Künstliche Intelligenz kindgerecht in Schulen bringt. Ziel ist, Kinder und Jugendliche frühzeitig mit KI vertraut zu machen, kritisches Denken zu fördern und Begeisterung für Forschung und Technik zu wecken.

## 🚀 Live Demo

The webpage is deployed on GitHub Pages: [https://kiwi-fhooe.github.io/kiwi-webpage/](https://kiwi-fhooe.github.io/kiwi-webpage/)

## 🛠️ Development

### Prerequisites
- Node.js 18+ 
- npm

### Local Development
```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## 📦 Deployment

### Automatic Deployment (GitHub Actions)
The webpage automatically deploys to GitHub Pages when changes are pushed to the `main` branch.

### Manual Deployment
```bash
# Build and deploy to GitHub Pages
npm run deploy
```

## 🎨 Features

- **Responsive Design**: Works on all devices
- **Smooth Scrolling**: Full-page sections with snap scrolling
- **Dynamic Colors**: Random background colors on page load
- **Interactive Elements**: Hover effects and smooth transitions
- **Back to Top**: Floating button for easy navigation
- **Modern UI**: Clean, professional design with KIWi branding

## 🏗️ Tech Stack

- **Vue.js 3**: Frontend framework
- **Vite**: Build tool and development server
- **CSS3**: Styling with custom properties
- **GitHub Pages**: Hosting platform
- **GitHub Actions**: CI/CD pipeline

## 📁 Project Structure

```
kiwi-webpage/
├── .github/workflows/    # GitHub Actions
├── public/              # Static assets
├── src/                 # Source code
│   ├── App.vue         # Main component
│   ├── main.js         # Entry point
│   └── styles/         # CSS styles
├── dist/               # Build output
└── package.json        # Dependencies
```

## 🎯 Sections

1. **Hero**: Dynamic background with KIWi branding
2. **Goals**: Project objectives and targets
3. **Modules**: Educational modules by school level
4. **Partners**: Consortium members and collaborators
5. **Schools**: Participating educational institutions
6. **Benefits**: Value proposition for all stakeholders
7. **Funding**: Project funding and cooperation grants
8. **Contact**: Project contact information

## 🔧 Configuration

### GitHub Pages Setup
1. Go to repository Settings → Pages
2. Select "GitHub Actions" as source
3. The workflow will automatically deploy on push to main

### Custom Domain (Optional)
To use a custom domain:
1. Add `CNAME` file to `public/` directory
2. Configure DNS settings with your domain provider
3. Update GitHub Pages settings

## 📝 License

This project is licensed under the ISC License.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📞 Contact

For questions about the KIWi project, please contact the Softwarepark Hagenberg team.