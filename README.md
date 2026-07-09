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

### npm Scripts

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

### 🤖 Claude Custom Commands

This starter kit includes custom commands to speed up development:

#### `/add-page <page-name>`
Creates a new Next.js page with Header, default layout, and Card components.

```bash
/add-page about
/add-page blog/featured-posts
/add-page docs/getting-started
```

**What it does:**
- Creates `app/<page-name>/page.tsx` with full page template
- Includes Header component and responsive layout
- Uses Tailwind CSS and Card components for styling
- Auto-generates TypeScript with proper typing

#### `/add-component <component-name> [--ui]`
Creates a new React component with TypeScript and Tailwind CSS.

```bash
/add-component Hero
/add-component UserCard --ui
/add-component BlogHeader
```

**What it does:**
- Creates `components/<component-name>.tsx` (or `components/ui/` with `--ui` flag)
- Includes JSDoc comments and TypeScript interfaces
- Sets up Props type with React.HTMLAttributes
- Uses `cn()` utility for class merging

---

## 🤖 Claude Subagents

This starter kit includes specialized subagents for different development tasks.

### `component-generator`
**Expert React component creator and optimizer**

- **Role**: Automatically generates React components with TypeScript and Tailwind CSS
- **Features**:
  - TypeScript Props interfaces
  - JSDoc documentation
  - Accessibility (a11y) checking
  - shadcn/ui component suggestions
  - Code quality optimization

- **Usage**: 
```
@component-generator: Create a UserProfile component that shows user name, email, and avatar
```

### `page-builder`
**Next.js page creation and routing specialist**

- **Role**: Creates Next.js pages with proper structure, layouts, and SEO metadata
- **Features**:
  - Automatic page.tsx generation
  - Layout management
  - Metadata/SEO setup
  - Dynamic routing support
  - Responsive design

- **Usage**:
```
@page-builder: Create a blog/featured-posts page with post list, filtering, and pagination
```

### How to Use Subagents

In Claude Code, you can invoke subagents using the `@agent-name` syntax:

```
@component-generator: Make a ProductCard component with image, price, and add-to-cart button

@page-builder: Create a pricing page with pricing tiers and features comparison
```

Subagents work independently with specialized knowledge and tools, making them perfect for:
- **component-generator**: UI component creation and optimization
- **page-builder**: Page structure and routing setup
- Future additions: test-runner, security-checker, performance-analyzer, etc.

---

## 🪝 Claude Hooks (Automation)

Hooks automatically execute shell commands in response to specific events. They're configured in `.claude/settings.json`.

### Enabled Hooks

#### ✨ Auto-formatting (PostToolUse)
Automatically formats `.ts`, `.tsx`, `.js`, `.jsx`, and `.json` files with Prettier after they're created or modified.

**Example:**
```
1. You create a new component with /add-component
2. ✅ File is automatically formatted by prettier
3. Code style is consistent automatically
```

#### 🔒 File Protection (PreToolUse)
Prevents accidental modification of sensitive files:
- `.env` / `.env.local` - Environment variables
- `package-lock.json` / `yarn.lock` - Dependency locks

**Example:**
```
1. You attempt to edit .env
2. ❌ Hook blocks the edit
3. "Cannot modify protected file" warning is shown
```

#### 📝 Command Logging (PostToolUse)
Logs all bash commands executed by Claude to `.claude/bash-log.txt`.

**Example Log:**
```
npm run build - Production build
git push origin main - GitHub에 저장소 푸시
npm run dev - Development server
```

### Configuration

Hooks are defined in `.claude/settings.json`:
- `PostToolUse`: Runs after a tool executes
- `PreToolUse`: Runs before a tool executes (can block execution)

For detailed hook information, see [`.claude/HOOKS.md`](./.claude/HOOKS.md).

### Adding New Hooks

1. Edit `.claude/settings.json`
2. Add hook to appropriate event with:
   - `matcher`: Tool to trigger on (e.g., "Edit|Write", "Bash")
   - `command`: Shell command to execute
3. Restart Claude Code

**Example - Add notification on success:**
```json
{
  "PostToolUse": [
    {
      "matcher": "Bash",
      "command": "[ $? -eq 0 ] && echo '✅ Done!' || echo '❌ Failed!'"
    }
  ]
}
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
