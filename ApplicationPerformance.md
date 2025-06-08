How to make application performance-
--------------------------------------

so let's say if you are using a list of items if you are entering list of item on the screen
and if it's a use list then it's better to use infinite scrolling instead of displaying all the items in one go.

If you are using some image then get the image in low resolution in the form of thumbnail and then whenever user clicks it you get the actual image so that will make it performant and also we can use
lazy loading and functional components.

There are several performance optimization techniques in React and it totally depends on the use case -
prevents unnecessary re-renders of functional components the hook
useMemo → Memoizes a value (avoids re-calculating)
useCallback → Memoizes a function (avoids re-creating it)



Here's a short and effective way to explain React optimization in an interview:


---

“React optimization is about improving app performance and responsiveness. I follow several key strategies:

1. Component Reusability & Splitting: I break components into smaller, reusable pieces to avoid unnecessary renders.
2. Memoization: I use React.memo, useMemo, and useCallback to prevent re-renders and recalculations when dependencies haven't changed.
3. Lazy Loading & Code Splitting: I implement lazy loading with React.lazy and Suspense to load components only when needed.
4. Virtualization: For large lists, I use libraries like react-window to render only visible items.
5. State Management Optimization: I minimize prop drilling by using Context, and I localize state as much as possible to reduce re-renders.
6. Avoid Anonymous Functions in JSX: I define functions outside the render method to prevent re-renders.
7. Efficient DOM Updates: I avoid frequent state updates and batch updates where possible.
8. Use DevTools: I use React Developer Tools and Chrome Performance tab to detect and resolve bottlenecks.”



* Accessibility.md
* Carousel-Performance-Optimisation.md
* Client-vs-Server-Side-Rendering.md
* CodeSplitting.md
* ErrorBoundaries.md
* HOC-Pattern.md
* ModulePattern.md
* ReactProfiler.md
* RenderProps.md
* Virtualization.md
* WebVitals.md


"I use multiple techniques to optimize performance and improve user experience in React apps, depending on the scenario.

For accessibility, I follow best practices like semantic HTML, ARIA roles, and keyboard navigation. In a recent dashboard project, making buttons accessible helped improve both usability and SEO.

For carousels, I lazy-load images and render only a few slides at a time. This helped reduce DOM load and made the homepage much faster, especially on mobile.

When it comes to client-side vs server-side rendering, I prefer SSR using Next.js for SEO-critical pages like blogs or product details, while using CSR for dynamic pages like dashboards.

Code splitting is another key area—I use React.lazy and Suspense to load components only when needed. This helped reduce the initial bundle size significantly in one of my projects.

I also implement Error Boundaries to catch runtime errors in parts of the app and display a fallback UI, preventing the whole app from crashing. We used this for a payment section that sometimes received unstable data.

For reusability, I use HOCs for wrapping logic like auth or theming. It helped reduce repeated logic across components. Similarly, I apply the module pattern to encapsulate helper functions and keep the codebase clean.

Using the React Profiler, I identify slow or unnecessary re-renders. In one case, I noticed a component re-rendering on every keystroke, so I optimized it using useCallback.

I’ve also worked with render props to create reusable data-fetching components, and virtualization for large lists or tables using react-window, which drastically improved scroll performance.

Lastly, I monitor Web Vitals like LCP, CLS, and FID. Once, I fixed a layout shift issue caused by dynamic banners by reserving space using aspect ratios.”_

