# 🚀 Supreme Group Website

This is the official website for **Supreme Group**, built with [Next.js](https://nextjs.org/) and styled using [Tailwind CSS](https://tailwindcss.com/). The site includes animated hero sections, tabbed product showcases, and a responsive contact form — all optimized for performance and accessibility.

Live Demo: https://blacksof-supreme-group.vercel.app/

---

For this project, I opted to use local React state (useState, useRef, and useEffect) rather than integrating a global state management library such as Context API, Redux, or Zustand.

✅ Rationale
Component-level state was sufficient for handling all interactive behaviors, such as:
Form input handling and feedback
Video playback state
Scroll and visibility control
The application does not share state extensively across deeply nested components, eliminating the need for global context or reducers.
Adding a global store would have introduced unnecessary complexity and overhead without substantial benefit for the current scope.

📌 Conclusion
React’s built-in hooks provided a clean, efficient, and maintainable way to manage state in this UI-driven project. Should the application scale further (e.g., dynamic content loading, authentication flows, or global modals), a more robust state management solution can be introduced incrementally.



1. 🛠️ Project Setup Instructions

```bash
git clone https://github.com/Sanyam7/Blacksof-supreme-group.git
cd Blacksof-supreme-group
npm install
npm run dev
```

2. Component Architecture Overview
The app uses a modular file structure for reusability and clarity:

```plaintext
src/
├── app/ # Next.js 13+ App directory
├── components/ # Reusable UI components
│ ├── navbar/ # Responsive navbar
│ ├── hero/ # Hero section with video/text
│ ├── features/ # Tabbed feature sections (e.g., Passenger, Commercial)
│ ├── contact/ # Contact form with toast feedback
│ └── footer/ # Sticky responsive footer
├── public/ # Static assets (videos/images)
└── styles/ # Global styles and Tailwind config
```

Each section is broken into its own component file (e.g., HeroVideoDesktop.jsx, ContactForm.jsx, etc.)
Responsiveness is handled through Tailwind’s responsive utilities.
Shared utilities like animations and transitions are abstracted when needed




3. Responsive Design Strategy:
      ### Responsive Design Strategy
   
   | Feature            | Implementation Details                                                                 |
   |--------------------|-----------------------------------------------------------------------------------------|
   | Breakpoints        | Used `sm`, `md`, `lg`, `xl`, and `2xl` classes for adaptive layouts                    |
   | Layouts            | Leveraged `grid` and `flex` utilities for column switching and stacking on smaller screens |
   | Media Switching    | Used `lg:hidden` and `hidden lg:block` for device-specific video/image rendering       |
   | Font Scaling       | Responsive typography using `text-base`, `text-lg`, `text-2xl`, etc.                   |




4. Performance Optimization Techniques:

  - Lazy loading of videos and heavy sections to defer initial load.
  - Memoization using `useMemo` for frequently rendered data (e.g., parts list).
  - Conditional rendering of large components (e.g., switching between mobile and desktop hero).
  - Next.js image optimization or fallback to optimized formats in the `/public` directory.
  - CSS animations triggered only when in viewport (via Intersection Observer or scroll events).
  - Reduced unnecessary re-renders through proper usage of `key` props and isolated state updates.



5. Accessibility Considerations


  | Area                 | Implementation Details                                                                 |
  |----------------------|-----------------------------------------------------------------------------------------|
  | Form Accessibility   | Labels are linked to inputs using `htmlFor` and `id`. Validation uses `aria-invalid`.  |
  | Keyboard Navigation  | Buttons and inputs are accessible. Modal can support ESC key for close (enhancement).  |
  | Focus Indicators     | Used Tailwind’s `focus-visible` classes (`focus:outline-none`, `focus-visible:border-white`). |
  | Alt Text & ARIA      | Images/videos should use descriptive `alt` attributes or `aria-label` for clarity.     |





6. Third-Party Libraries Used
Library	Purpose
- framer-motion:	Smooth animations and transitions
- animate.css:	Simple toast/modal animations
- next/image: Optimized image handling
- Tailwind CSS:	Utility-first styling




7. Assumptions & Decisions:
- Chose Tailwind CSS over traditional CSS for rapid UI development and responsiveness.
- Used Framer Motion selectively to avoid animation overhead.
- Avoided client-heavy libraries (like Swiper) unless necessary.
- Componentized each major section (Hero, Navbar, Footer) for better maintainability.





8. Challenges Faced & Solutions
 

  | Challenge                                | Solution                                                                                         |
  |------------------------------------------|--------------------------------------------------------------------------------------------------|
  | Embedding autoplaying video in background | Used `muted`, `autoPlay`, `loop`, and `playsInline` to ensure consistent playback across devices. |
  | Smooth scroll between sections            | Implemented `ref` + scroll handler with smooth animation on tab switch.                          |
  | Tab switching performance lag (on mobile) | Applied debounce on scroll events and memoized heavy components to reduce re-renders.            |






9. Upcoming Features / Improvements:
- Backend integration for Contact Form (e.g., EmailJS or API route)
- SEO and metadata improvements
- Add multi-language support via next-intl
- Unit tests for reusable components (with Jest + React Testing Library)

