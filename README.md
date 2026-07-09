# Claude Next.js Starter Kit

A modern, production-ready Next.js starter template with Tailwind CSS, shadcn/ui components, and TypeScript.

## 🚀 Features

- **Next.js 15** - Latest features with App Router and Server Components
- **shadcn/ui** - High-quality, accessible React components
- **Tailwind CSS** - Utility-first CSS framework for rapid UI development
- **TypeScript** - Full type safety and excellent developer experience
- **Dark Mode** - Built-in dark mode support with smooth transitions
- **Responsive Design** - Mobile-first approach included by default
- **Pre-configured Components** - Button, Card, Badge, and more
- **Example Pages** - Get started with real-world examples

## 📦 Tech Stack

- **Framework**: Next.js 15
- **Styling**: Tailwind CSS 4
- **UI Components**: shadcn/ui with Base UI
- **Icons**: Lucide React
- **Language**: TypeScript
- **Package Manager**: npm

## 🎯 Quick Start

### Prerequisites
- Node.js 18+ and npm

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd claude-nextjs-starterkit
```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

4. Open [http://localhost:3000](http://localhost:3000) in your browser

## 📁 Project Structure

```
├── app/
│   ├── layout.tsx          # Root layout with metadata
│   ├── page.tsx            # Home page
│   ├── examples/page.tsx   # Examples page
│   ├── components/page.tsx # Components documentation
│   └── globals.css         # Global styles and Tailwind config
├── components/
│   ├── ui/                 # shadcn/ui components
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   └── badge.tsx
│   └── header.tsx          # Custom header component
├── lib/
│   └── utils.ts            # Utility functions (cn helper)
├── public/                 # Static assets
├── package.json
├── tsconfig.json
├── tailwind.config.ts
├── next.config.ts
└── components.json         # shadcn/ui configuration
```

## 🛠️ Available Commands

```bash
# Development server
npm run dev

# Production build
npm run build

# Start production server
npm start

# Run ESLint
npm run lint
```

## 📝 Customization

### Add New shadcn/ui Components

```bash
npx shadcn-ui@latest add <component-name>
```

For example:
```bash
npx shadcn-ui@latest add input
npx shadcn-ui@latest add dialog
npx shadcn-ui@latest add select
```

### Customize Theme Colors

Edit `app/globals.css` to modify the CSS variables:

```css
:root {
  --primary: oklch(...);
  --secondary: oklch(...);
  /* More colors */
}
```

### Update Tailwind Config

Modify `tailwind.config.ts` for custom configuration like spacing, fonts, etc.

## 🧩 Included Components

- **Button** - Versatile button component with variants
- **Card** - Container component with header, content, and footer
- **Badge** - Small label component for status indication
- **Header** - Navigation header with responsive design

## 📚 Resources

- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [shadcn/ui Documentation](https://ui.shadcn.com)
- [TypeScript Documentation](https://www.typescriptlang.org/docs)

## 🚢 Deployment

### Deploy on Vercel (Recommended)

1. Push your code to GitHub
2. Visit [Vercel](https://vercel.com/new)
3. Import your repository
4. Vercel will automatically detect Next.js and configure the build settings
5. Click "Deploy"

### Deploy on Other Platforms

This starter kit can be deployed on any platform that supports Node.js:
- Netlify
- Railway
- Heroku
- AWS
- DigitalOcean
- And more...

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues and pull requests.

## 💡 Tips

- Use the Examples page to see different component combinations
- Check the Components page for usage documentation
- Customize the Header component for your branding
- Use `cn()` utility from `lib/utils.ts` for merging Tailwind classes

---

Built with ❤️ using Claude Code
