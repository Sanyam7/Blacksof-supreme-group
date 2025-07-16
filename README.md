# Supreme Group – Frontend Implementation

This project is a frontend implementation of the **Supreme Group** website, built as a technical task for **Blacksof**. It closely follows the provided Figma design and fulfills all required specifications using **Next.js**, **Tailwind CSS**, and modern web development best practices.

## Live Demo

[Deployed on Vercel](https://supreme-app.vercel.app/)

## Repository

[GitHub Repository](https://github.com/Yashskamble/SupremeGroup)

---

## Tech Stack

| Category             | Tech Used                               | Reasoning                                                                       |
| -------------------- | --------------------------------------- | ------------------------------------------------------------------------------- |
| **Framework**        | [Next.js](https://nextjs.org)           | Chosen for its file-based routing, built-in SSR, SEO benefits, and performance. |
| **Language**         | JavaScript (ES6+)                       | Offers rapid prototyping and is widely used with React ecosystem.               |
| **Styling**          | [Tailwind CSS](https://tailwindcss.com) | Provides utility-first responsive design and excellent developer experience.    |
| **State Management** | React State                             | Sufficient for the scope; avoids over-engineering with Redux/Zustand.           |
| **Hosting**          | [Vercel](https://vercel.com)            | Optimized for Next.js deployments and provides free hosting.                    |

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/Yashskamble/SupremeGroup.git
cd SupremeGroup
```

### 2. Install dependencies

```bash
npm install
# or
yarn
```

### 3. Run the project locally

```bash
npm run dev
# or
yarn dev
```

---

## Component Architecture

The project is structured into reusable, modular components under the `/components` folder. Major UI sections such as Hero, Tabs, and Video sections are divided based on atomic design principles.

```
/components
  ├── Header
  ├── HeroSection
  ├── VerticalTabs
  ├── VehicalPart
  ├── HeroVideoSlideMobile
  ├── HeroVideoDesktop
  └── ...
```

### Key Architecture Decisions:

- **Separation of Concerns:** Layouts and UI are separated for maintainability.
- **Props-Driven Components:** All dynamic sections are configurable via props or constants.
- **Constants Directory:** All static content (like tabs and images) is stored centrally for cleaner component logic.

---

## Responsive Strategy

Responsive design is implemented using Tailwind's mobile-first utility classes.

- Used `sm`, `md`, `lg`, `xl`, `2xl` breakpoints for granular control.
- Tested on Chrome, Firefox, Safari for mobile and desktop views.
- Layouts adapt for:
  - Mobile (≤768px)
  - Tablet (769px–1024px)
  - Laptop/Desktop (≥1025px)

---

## Performance Optimization

- **Image Optimization:** Used `next/image` for automatic image optimization.
- **Static Assets:** Served through Next.js’ `public` folder to leverage caching.

---

## Accessibility Considerations

Implemented following **WCAG** and **ARIA** standards:

- Semantic HTML tags (`<section>`, `<header>`, `<nav>`, `<button>`, etc.)
- Keyboard navigability
- ALT tags for all images
- Focus outlines for accessibility navigation

---

## Animations

Used **Framer Motion** for smooth and performant scroll-in and tab-based animations:

- Vertical tab transitions
- Subtle fade-in and slide effects on sections

---

## Testing (Optional Scope)

Testing wasn't implemented due to the limited timeframe but can be added using:

- **Unit Tests:** React Testing Library + Jest

---

## Third-Party Libraries

| Library                | Usage                                     |
| ---------------------- | ----------------------------------------- |
| `framer-motion`        | Smooth scroll and tab-based animations    |
| `next/image`           | Image optimization and responsive loading |
| `classnames` (if used) | Conditional class utility (optional)      |

---

## Assumptions & Decisions

- Only desktop and mobile designs were available. Tablet layouts were inferred based on responsive best practices.
- Static images and data are used from the provided design. No backend API integration assumed.

---

## Challenges Faced

| Challenge                 | Solution                                                                |
| ------------------------- | ----------------------------------------------------------------------- |
| Precise Figma replication | Used Tailwind spacing and typography utilities for pixel-perfect design |

---

## Final Remarks

This project demonstrates a performant, accessible, and responsive frontend build aligned with modern standards and design fidelity. Feel free to reach out for any clarification or walkthrough.
