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
Tailwind CSS breakpoints: Used sm, md, lg, xl, and 2xl classes for adaptive layouts.
grid & flex layouts: Used to handle column switching and vertical stacking on smaller devices.
Video/image swaps: Conditional rendering between desktop and mobile using lg:hidden, hidden lg:block to provide device-specific UIs.
Font scaling: Dynamic typography via text-base, text-lg, text-2xl, etc.



4. Performance Optimization Techniques:
Lazy loading videos and heavy sections to defer initial load.
Memoization (useMemo) of repeated render data (e.g., parts list).
Conditional rendering for large components (e.g., mobile vs desktop hero).
Next.js image optimization or fallback to optimized formats in /public.
CSS animations only when in view (using intersection observer / scroll events).
Minimized re-renders through proper key props and state updates.



5. Accessibility Considerations

Form accessibility:
Labels are associated with inputs using htmlFor and id.
Validation errors are announced with aria-invalid.

Keyboard navigation:
Buttons and inputs are keyboard accessible.
Close modal via keyboard (ESC) logic can be added for enhanced UX.

Focus indicators:
Tailwind’s focus-visible states are used (focus:outline-none, focus-visible:border-white).

Alt text & ARIA:
Images/videos (if added) should use appropriate alt or aria-labels




6. Third-Party Libraries Used
Library	Purpose
framer-motion:	Smooth animations and transitions
animate.css:	Simple toast/modal animations
next/image: Optimized image handling
Tailwind CSS:	Utility-first styling




7. Assumptions & Decisions:
Chose Tailwind CSS over traditional CSS for rapid UI development and responsiveness.
Used Framer Motion selectively to avoid animation overhead.
Avoided client-heavy libraries (like Swiper) unless necessary.
Componentized each major section (Hero, Navbar, Footer) for better maintainability.





8. Challenges Faced & Solutions
 
Embedding autoplaying video in background:	Used muted, autoPlay, loop, playsInline to ensure it plays on all devices
Smooth scroll between sections:	Added ref + scroll handler on tab switch to enable animated scrolling
Tab switching performance lag (on mobile):	Debounced scroll events, and memoized content rendering






9. Upcoming Features / Improvements:
Backend integration for Contact Form (e.g., EmailJS or API route)
SEO and metadata improvements
Add multi-language support via next-intl
Unit tests for reusable components (with Jest + React Testing Library)

