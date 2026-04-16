<div align="center">

# 🌸 for you

A minimalist, animated, one-page web experience created as a poetic greeting.

[Live Demo](#) · [Report Bug](#) · [Request Feature](#)

</div>

## 📖 About The Project

**"for you"** is a delicate, interactive web poem. It combines a beautiful SVG flower garden animation with a softly appearing poetic text. The project is designed to be a digital greeting card or a personal message that unfolds gracefully before the reader's eyes.

### ✨ Features

- **Animated Intro:** A stunning SVG flower garden that grows and blooms, powered by GSAP and DrawSVG.
- **Scroll-Triggered Poetry:** Stanzas of a poem that gently fade in as the user scrolls down the page.
- **Atmospheric Design:** A dark, moody background featuring a rose, complemented by elegant typography (`Great Vibes` and `Special Elite`).
- **Responsive:** Looks beautiful on both desktop and mobile devices.

### 🛠 Built With

- [React](https://reactjs.org/)
- [Vite](https://vitejs.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS v4](https://tailwindcss.com/)
- [GSAP](https://greensock.com/gsap/) (for SVG animation)

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

Make sure you have Node.js and `pnpm` installed.

```sh
npm install -g pnpm
```

### Installation

1. Clone the repo
   ```sh
   git clone https://github.com/sofisideris-cmd/happy.git
   ```
2. Install NPM packages
   ```sh
   cd happy
   pnpm install
   ```
3. Start the development server
   ```sh
   pnpm run dev
   ```

## 📝 Customization

You can easily customize the text of the poem to make it your own!

1. Open `src/app/App.tsx`.
2. Locate the `stanzas` array at the top of the file.
3. Edit the `lines` within each stanza object. You can also use the `isTitle`, `isSpecial`, or `isClosing` flags to apply different styling to specific stanzas.

## 📜 Acknowledgements

- The beautiful SVG flower animation was originally inspired by [flowers_garden](#) (HTML/CSS/JS).
- Background rose image provided within the project assets.
- Fonts provided by Google Fonts.

---
<div align="center">
  Made with ❤️ by Sofi
</div>
# happy
