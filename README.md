

# 📚 personal-library

This project is a **Nuxt-based personal library** where I store all reusable components, layouts, UI snippets and utilities I might need in future digital projects.  
It serves as a development playground and a reference hub to speed up future builds.

## 🧱 Tech Stack

- **Nuxt 3** – The core framework
- **Tailwind CSS** – Utility-first styling
- **Lucide Icons** – For elegant, modern icons
- **Optional CSS** – Some components may use plain CSS when necessary

---

## 📦 Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/your-username/personal-library.git
cd personal-library
npm install
```

## 🧩 Icons

To install Lucide icons (used throughout the library):

```bash
Copier
Modifier
npm install lucide-vue-next
Usage example in a component:
```
```bash
<script setup>
import { Copy } from 'lucide-vue-next'
</script>

<template>
  <Copy class="w-5 h-5" />
</template>
```

# Nuxt Minimal Starter

Look at the [Nuxt documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Setup

Make sure to install dependencies:

```bash
# npm
npm install

# pnpm
pnpm install

# yarn
yarn install

# bun
bun install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev

# pnpm
pnpm dev

# yarn
yarn dev

# bun
bun run dev
```

## Production

Build the application for production:

```bash
# npm
npm run build

# pnpm
pnpm build

# yarn
yarn build

# bun
bun run build
```

Locally preview production build:

```bash
# npm
npm run preview

# pnpm
pnpm preview

# yarn
yarn preview

# bun
bun run preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.
