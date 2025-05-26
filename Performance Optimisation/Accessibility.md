 How do you test for accessibility issues in your code?
 --------------------------------------------------------

I use a combination of manual and automated testing techniques:

Automated Tools:
---------------------
* axe DevTools and Lighthouse (built into Chrome) to scan for common accessibility issues.
* eslint-plugin-jsx-a11y during development to catch issues early in JSX.


Manual Testing:
--------------------
* Keyboard Navigation: I navigate the application using only the keyboard (Tab, Shift+Tab, Enter, Esc,  etc.) to ensure all actions are accessible.
* Screen Readers: I use NVDA (Windows) or VoiceOver (Mac) to test how screen readers interpret my UI.
* Color Contrast Checkers: I use tools like the WebAIM Contrast Checker to validate sufficient contrast.

--------------------------------------------------------------------------------------------------------

Can you provide an example where you improved the accessibility of a web application?
 ---------------------------------------------------------------------------------------
Yes. In a previous project, I worked on an internal dashboard that was not accessible to screen readers and had poor keyboard navigation. Here's what I did to improve it:

* I replaced many div-based buttons with semantic <button> elements and added meaningful aria-labels for icons.
* I audited all forms and ensured every input had a corresponding <label> or aria-labelledby.
* I restructured the headings to follow a logical hierarchy (h1 for main title, h2 for sub-sections, etc.) to improve screen reader navigation.
* I implemented a visible focus outline and ensured tab order flowed logically.
* I used Lighthouse and axe DevTools to test and fix accessibility violations.

After these changes, the dashboard passed WCAG AA compliance checks and significantly improved usability for users with assistive technologies.

-------------------------------------------------------------------------------------------------------

What are some accessibility best practices you follow during development?
 ---------------------------------------------------------------------------
I follow several key accessibility best practices to ensure that web applications are usable by everyone, including people with disabilities:

* Semantic HTML: I use proper HTML elements for their intended purposes, such as < button > for actions, < form > for form groups, and appropriate heading levels (< h1 > to < h6 >) to ensure screen reader compatibility.

* Alt Text: I ensure that all meaningful images have descriptive alt attributes, and decorative images have alt="".

* Keyboard Navigation: I make sure that all interactive elements are accessible via keyboard (Tab, Enter, Space, etc.) and avoid using div or span for clickable elements unless properly handled with ARIA roles.

* ARIA Attributes: I use ARIA roles and properties where necessary to enhance semantics (like aria-label, aria-expanded, etc.), but I always prefer native elements first.

* Color Contrast: I verify sufficient color contrast between text and background to ensure readability for users with visual impairments.

* Focus Management: I manage focus properly during navigation (e.g., modals, form submissions) so screen readers and keyboard users can follow the flow of the application.

* Responsive Text & Layout: I avoid using fixed pixel sizes, opting for relative units to ensure the interface works well with zoom or screen magnification.
