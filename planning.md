### What location are you building this guide for, and why did you choose it?
-I chose Kigali, Rwanda because it is a small city in a small country that most people do not know about but has alot to offer. 

### Who is your primary audience? (e.g., first-time visitors, backpackers, families, local residents)
-Visitors, explorers, families, sports fans.

### What do you want visitors to feel or know after spending 5 minutes on your site?
-I want my website visitors to feel motivated and encouraged to visit Kigali so that they themselve can get to experience it. 

### What's one design decision — color, layout, or tone — that reflects your destination's identity?
-Nature(green) Light(blue)

## Design Document
### What color palette reflects your destination? Name three words that describe the feeling.
-White yellow blue and green Life and nature, aesthetic

### What typography (heading font / body font) fits your destination's character?
- **Heading font**: 'Brush Script MT', cursive - Elegant and flowing script that evokes the artistic and welcoming nature of Kigali
- **Body font**: 'Times New Roman', Times, serif - Classic and clean serif font for readability and professional appearance
- **Character fit**: The combination of decorative script for headlines with classic serif for body text creates a balance between personality and professionalism, reflecting Kigali's blend of modern growth and cultural heritage

### What's one visual choice that connects to your destination's identity?
- **Full-screen hero banner** with background image of Kigali cityscape
- **Nature-inspired color palette**: Light green-tinted text (#eaffe8) against natural backgrounds reflects Rwanda's "Land of a Thousand Hills" identity
- **White card-based layout** on soft background (#F8FAF7) represents cleanliness - Kigali is known as one of Africa's cleanest cities

### What are the three device sizes you're designing for, and what width defines each breakpoint?
1. **Desktop/Large screens**: Above 1024px (default styling)
   - Full-size banner title (300px font)
   - Multi-column card layouts (up to 3 cards per row)
   - Transparent navigation overlay on homepage
   
2. **Tablet/Medium screens**: 1024px and below
   - Reduced banner title (100px font)
   - Adjusted grid layout for better spacing
   - Cards begin to stack more densely
   
3. **Mobile/Small screens**: Below 768px (handled by flex-wrap)
   - Single-column card stacking (automatic via `flex: 1 1 280px`)
   - Full-width content
   - Sticky navigation remains accessible

### For each major section of your site, what needs to change at each breakpoint?
- **Banner/Hero section**: Font size scales from 300px → 100px to prevent overflow on smaller screens
- **Navigation**: Remains functional at all sizes; sticky positioning on subpages ensures constant access
- **Card grids** (Attractions/Activities/Photos):
  - Desktop: 2-3 cards per row with 360px max-width
  - Tablet: 2 cards per row
  - Mobile: 1 card per row (automatic stacking with `flex-wrap: wrap`)
- **Images**: Fixed height (190px) with `object-fit: cover` maintains aspect ratio across all devices
- **Gap spacing**: Consistent 20px gap maintained at all breakpoints

### Are there any sections where the mobile experience should feel meaningfully different from desktop, not just smaller?
- **Homepage hero banner**: On mobile, the massive 300px → 100px title reduction fundamentally changes the visual hierarchy from "immersive statement" to "readable greeting"
- **Navigation behavior difference**: 
  - Desktop homepage: Transparent overlay navigation (position: absolute) that floats above the hero image
  - Subpages + all mobile: Sticky navigation bar with solid background for better visibility and accessibility
- **Card interactions**: On mobile, single-column stacking creates a more focused, scrollable story experience rather than scanning across multiple columns
### Milestone 3
## What content does this section contain and how should it be arranged? (e.g., side by side, stacked, grid-like)
**Homepage (#Home section):**
- Contains a heading ("About Kigali") and descriptive paragraph
- **Current arrangement**: Stacked vertically with the heading taking full width and the text content in a white card below
- **Content**: Introduces Kigali as one of Africa's cleanest cities with information about its size, population, and character

## How many columns or items should appear in a row at desktop width?
**Homepage (#Home section):**
- **1 column layout** - Full-width text content
- The heading spans 100% width (`flex-basis: 100%`)
- The paragraph also spans 100% width (`flex: 1 1 100%`) in a white card
- This is intentional for readability - long-form text shouldn't stretch too wide

*(Note: Other sections like attractions, activities, and photos use 2-3 cards per row at desktop width with `max-width: 360px`)*

## How should that change on a smaller screen?
**Homepage (#Home section):**
- **No change needed** - already single column at all widths
- The white card with text remains full-width and readable
- Gap spacing (20px) and padding (20px) stay consistent
- This section naturally works well across all device sizes due to its simple stacked layout

## Is there anything about the spacing, alignment, or sizing that's important to the design?
**Yes, several key aspects:**
1. **White card on soft background**: Text sits in white (#FFFFFF) card against soft green-tinted background (#F8FAF7) - reflects Kigali's cleanliness
2. **Centered alignment**: All content is center-aligned (`text-align: center` on body)
3. **Consistent spacing**: 20px gap and padding throughout maintains visual rhythm
4. **Border radius**: 10px rounded corners on the white card creates a soft, approachable feel
5. **Full-width constraint**: Paragraph uses `flex: 1 1 100%` to ensure text doesn't break into multiple columns (important for readability)
