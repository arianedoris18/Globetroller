# Globetrotter — Decisions Log

## Milestone 0: Setup and Planning
- Destination chosen: Kigali, Rwanda
- Primary audience: Tourists, Explorers
- One design decision that reflects the destination: Color 
- Wireframe format used (hand-drawn / Figma / other):hand-drawn

## Milestone 1: HTML Structure
- **Pages created**: 4 pages total (index.html, top-attractions.html, activity-guide.html, photo-guide.html)
- **Navigation structure**: Consistent navigation menu across all pages using `<nav>` with unordered list
- **Semantic HTML elements used**: 
  - `<header>` for banner section
  - `<nav>` for navigation menu
  - `<section>` for main content areas
  - `<article>` for individual attraction/activity/photo cards
- **Content organization**: Each subpage uses card-based layout with images and descriptive text
- **Accessibility**: All images include alt text describing the content

## Milestone 2: CSS Styling
- **Color scheme**: Light background (#F8FAF7) with white cards (#FFFFFF) and green-tinted banner text (#eaffe8, #04270c) reflecting Rwanda's natural landscape
- **Typography**: 'Brush Script MT' for hero title (decorative), Times New Roman for body text
- **Banner styling**: Full-screen hero banner with background image (Kiagali.webp), centered text overlay, min-height of 850px
- **Navigation styling**: 
  - Homepage: Transparent navigation positioned absolutely in top-right corner
  - Subpages: Sticky navigation with light blue background (#d2e7ff) for better visibility
- **Card design**: White rounded cards (10px border-radius) with consistent padding (14px) and shadow-like appearance on light background

## Milestone 3: Flexbox Layout
- **Navigation**: `display: flex` with `justify-content: flex-end` for right-aligned menu items
- **Banner**: `display: flex` with `flex-direction: column`, `align-items: center`, and `justify-content: center` for centered hero content
- **Top Attractions section**: `flex-direction: row` with `flex-wrap: wrap` for responsive card grid
  - Cards: `flex: 1 1 280px` with `max-width: 360px` for flexible sizing
- **Activity Guide section**: Same flexbox pattern as Top Attractions for consistency
- **Photo Guide section**: Similar flex layout allowing 5 photos to wrap responsively
- **Home section**: Flexbox layout for clean text presentation
- **Gap property**: 20px gap between all flex items for consistent spacing

## Milestone 4: Responsive Design
- **Media query breakpoint**: `@media screen and (max-width: 1024px)` for tablet/smaller screens
- **Responsive adjustments**:
  - Banner title font-size reduced from 300px to 100px for better fit on smaller screens
  - Grid layout adjustments defined for header, menu, content, facts, and footer areas
- **Mobile-first considerations**: 
  - Flexible card widths (`flex: 1 1 280px`) ensure cards stack on narrow screens
  - `flex-wrap: wrap` allows content to reflow naturally
  - Images use `object-fit: cover` to maintain aspect ratio at fixed 190px height

### What breakpoints did you end up using, and why those values?
I used **1024px as my primary breakpoint** (`@media screen and (max-width: 1024px)`). I chose this value because:
- **1024px is the standard tablet landscape width** (iPad landscape is exactly 1024px), making it a natural boundary between desktop and tablet experiences
- My hero title at 300px font size became illegible and overflowed on anything smaller than desktop screens, so 1024px was the threshold where I needed significant adjustments
- The **implicit mobile breakpoint happens naturally through flexbox** - my card flex-basis of 280px means cards automatically stack single-column on screens narrower than ~600-700px without needing an explicit media query
- This **two-tier approach** (explicit @ 1024px, implicit via flexbox) kept my CSS simple while covering three device categories: desktop (>1024px), tablet (768-1024px), and mobile (<768px)

### One section where the mobile layout needed to feel genuinely different, and what you did.
**The homepage hero banner** required a fundamentally different mobile experience, not just scaling:
- **Desktop experience**: Massive 300px "Explore Kigali" title dominates the full-screen banner, creating an immersive, cinematic first impression where the typography IS the hero
- **Mobile transformation (at 1024px breakpoint)**: Reduced title to 100px, which changes the entire visual hierarchy from "overwhelming statement piece" to "readable greeting"
- **Why genuinely different**: This wasn't just "make it smaller" - it shifted the banner's purpose from an immersive visual experience to a functional header. On mobile, users need to quickly understand where they are and access navigation, not spend time absorbing a massive artistic title. The 300px → 100px change (67% reduction) fundamentally rebalanced the page from "hero image with text overlay" to "header with background image"

### One Claude suggestion about breakpoints you accepted or rejected, and why.
**Suggestion I would have accepted**: Using flexbox's natural wrapping behavior instead of writing separate media queries for every screen size
- **Why**: My implementation already uses `flex: 1 1 280px` with `flex-wrap: wrap`, which means cards automatically reflow at any screen size without hardcoded breakpoints. This is smarter than writing `@media (max-width: 768px)`, `@media (max-width: 480px)`, etc. - the layout adapts fluidly to ANY device width
- **Result**: I only needed ONE explicit media query (1024px) for the hero title, while everything else responds organically

**Suggestion I would have rejected**: Adding a breakpoint specifically for very small phones (320px-375px)
- **Why rejected**: My flex-basis of 280px already ensures cards fit comfortably on even the smallest modern phones (iPhone SE is 375px wide). Adding another breakpoint would be over-engineering for diminishing returns
- **The tradeoff**: Simpler CSS and easier maintenance vs. hyper-optimization for edge cases that flexbox already handles gracefully