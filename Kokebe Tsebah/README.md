# Kokebe Tsibah School Website — Documentation

Welcome to the documentation for the **Kokebe Tsibah Secondary & Preparatory School** website. This project is built using **pure HTML5** and **Bootstrap 5 CDN**, without any custom CSS files, JavaScript frameworks, or build dependencies.

---

## 1. Project Overview & Architecture

### Core Design Philosophy

- **100% CDN-Based**: All styling and interactive widgets run directly from standard Content Delivery Network (CDN) links.
- **No Build Step Required**: You can open any `.html` file directly in any modern browser (Chrome, Safari, Edge, Firefox) by double-clicking it.
- **Human-Readable Code**: Structured with clean semantic HTML tags (`<nav>`, `<header>`, `<main>`, `<section>`, `<footer>`, `<form>`).
- **Fully Responsive**: Adapts automatically to mobile phones (320px–480px), tablets (768px), laptops (1024px), and desktop monitors (1440px+).

---

## 2. File Structure

```text
├── index.html          # Home page (Hero banner, Heritage, Campus Life, FAQ, Contact CTAs)
├── about.html          # About page (History, Campus photo with Amharic badge, Guiding Values)
├── contact.html        # Contact page (Location details, phone/email, interactive message form)
├── assets/             # Local images used across the site
│   ├── school-logo.png       # School crest logo (320x320 PNG)
│   ├── hero-classroom.jpg    # Students in science classroom
│   ├── lab-circuit.jpg       # Students conducting electrical circuit experiments
│   └── chem-lab.jpg          # Students conducting chemistry titration experiments
└── README.md           # This documentation guide
```

---

## 3. The 3 CDN Links Used

Every HTML page includes these three standard links from the official jsDelivr CDN:

### 1. Bootstrap 5.3.3 CSS (in `<head>`)

```html
<link
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
  rel="stylesheet"
/>
```

- **What it is**: The compiled Bootstrap styling library.
- **Functionality**: Provides all layout systems (grid, containers, flexbox), typography, cards, buttons, accordions, and spacing utilities.

### 2. Bootstrap Icons 1.11.3 (in `<head>`)

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css"
/>
```

- **What it is**: An official icon font containing thousands of vector icons.
- **Functionality**: Renders crisp icons such as `<i class="bi bi-check-circle-fill"></i>`, `<i class="bi bi-telephone-fill"></i>`, and `<i class="bi bi-envelope-fill"></i>` without needing image files.

### 3. Bootstrap 5.3.3 JavaScript Bundle (before `</body>`)

```html
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
```

- **What it is**: Bootstrap's JavaScript engine (which includes Popper.js).
- **Functionality**: Automatically powers interactive components like the mobile hamburger menu toggle, the FAQ accordion expand/collapse, and alert dismissal via HTML `data-bs-*` attributes without needing you to write custom JS.

---

## 4. Bootstrap Classes Dictionary (Meaning & Functionality)

Here is a breakdown of every Bootstrap class used in this project:

### A. Layout & Grid

| Class                     | Meaning                   | Functionality                                                                                                                                 |
| ------------------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `.container`              | Responsive Container      | Centers content horizontally and provides responsive maximum widths (`540px`, `720px`, `960px`, `1140px`, `1320px`) depending on screen size. |
| `.row`                    | Grid Row                  | A flexbox wrapper that holds columns and manages negative margins so gutters align cleanly.                                                   |
| `.col-12`                 | 12-Column Width (100%)    | Makes an element occupy the full width (12/12 columns) on small screens (mobile).                                                             |
| `.col-md-4`               | 4-Column Width on Tablets | On screens ≥ 768px, occupies 4/12 columns (one-third width), creating a 3-column grid.                                                        |
| `.col-md-5` / `.col-md-7` | 5 & 7 Column Split        | Creates an asymmetrical 2-column layout (e.g., Contact Info on left 5/12, Form on right 7/12).                                                |
| `.col-lg-6`               | Half-Width on Desktops    | Occupies 6/12 columns (50% width) on screens ≥ 992px.                                                                                         |
| `.col-lg-8`               | Two-Thirds on Desktops    | Occupies 8/12 columns (centered via `.justify-content-center` for the FAQ).                                                                   |
| `.g-4`, `.g-lg-5`         | Gutter Spacing            | Sets the gap (gutter) between columns horizontally and vertically (`g-4` = 1.5rem, `g-lg-5` = 3rem on large screens).                         |

---

### B. Navigation Bar (Navbar)

| Class                       | Meaning                 | Functionality                                                                                                              |
| --------------------------- | ----------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `.navbar`                   | Navigation Bar Base     | Formats navigation headers with responsive flex alignment.                                                                 |
| `.navbar-expand-lg`         | Responsive Breakpoint   | Tells Bootstrap: _collapse into a mobile hamburger menu below 992px, and expand into a horizontal row at 992px and above_. |
| `.navbar-brand`             | Logo / Brand Styling    | Applies standard typography, padding, and alignment for the brand link.                                                    |
| `.navbar-toggler`           | Mobile Hamburger Button | The button that toggles the collapsed menu on mobile devices.                                                              |
| `.navbar-toggler-icon`      | Hamburger Bars Icon     | Renders the standard three horizontal lines icon inside the toggler.                                                       |
| `.collapse.navbar-collapse` | Collapsible Menu Area   | Hides navigation links on small screens until the toggler button is tapped.                                                |
| `.navbar-nav`               | Navigation List         | A lightweight `<ul>` flexbox list specifically tuned for nav links.                                                        |
| `.nav-item`                 | Navigation Item         | Wraps each navigation link.                                                                                                |
| `.nav-link`                 | Navigation Link         | Formats links with hover states, padding, and disabled/active color states.                                                |
| `.sticky-top`               | Pinned Header           | Keeps the navigation bar locked to the top of the browser window as the visitor scrolls down.                              |

---

### C. Flexbox Utilities

| Class                      | Meaning                 | Functionality                                                                                                    |
| -------------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------- |
| `.d-flex`                  | Display Flex            | Turns an element into a flexbox container.                                                                       |
| `.flex-column`             | Vertical Flex Direction | Stacks child elements vertically on top of each other.                                                           |
| `.flex-sm-row`             | Responsive Direction    | Stacks items vertically on phones (`< 576px`), and arranges them horizontally side-by-side on screens `≥ 576px`. |
| `.align-items-center`      | Vertical Alignment      | Centers flex children along the cross-axis (vertical center).                                                    |
| `.align-items-start`       | Top Alignment           | Aligns flex children to the top.                                                                                 |
| `.justify-content-center`  | Horizontal Centering    | Centers flex children along the main axis.                                                                       |
| `.justify-content-between` | Space Between           | Pushes the first item to the left and the last item to the right (used in footers).                              |
| `.justify-content-end`     | Align Right             | Pushes flex children to the far right (used to right-align desktop nav links).                                   |
| `.gap-2`, `.gap-3`         | Flex Gap                | Adds uniform spacing between child elements without writing manual margins (`gap-2` = 0.5rem, `gap-3` = 1rem).   |

---

### D. Typography & Colors

| Class                      | Meaning                | Functionality                                                                         |
| -------------------------- | ---------------------- | ------------------------------------------------------------------------------------- |
| `.display-5`, `.display-6` | Hero Display Headings  | Large, prominent heading styles designed for page titles and hero banners.            |
| `.fs-5`, `.fs-6`           | Font Size              | Sets font sizes based on Bootstrap's scale (`fs-5` = 1.25rem, `fs-6` = 1rem).         |
| `.lead`                    | Lead Paragraph         | Increases font size and lightens font weight for introductory paragraphs.             |
| `.fw-bold`                 | Font Weight: Bold      | Sets `font-weight: 700;`.                                                             |
| `.fw-semibold`             | Font Weight: Semi-Bold | Sets `font-weight: 600;`.                                                             |
| `.fw-medium`               | Font Weight: Medium    | Sets `font-weight: 500;`.                                                             |
| `.text-primary`            | Primary Blue           | Applies Bootstrap's official royal blue color (`#0d6efd`).                            |
| `.text-secondary`          | Secondary Gray         | Applies soft gray text (`#6c757d`), great for body copy.                              |
| `.text-muted`              | Muted Subtitle Color   | A softer muted tone for captions, subtitles, and dates.                               |
| `.text-light`              | Light White Text       | Light color for text placed over dark images/backgrounds.                             |
| `.text-dark`               | Near-Black Text        | High contrast dark color (`#212529`).                                                 |
| `.text-uppercase`          | Uppercase Transform    | Automatically capitalizes all letters (used on small badges/headers).                 |
| `.text-center`             | Center Alignment       | Centers text.                                                                         |
| `.text-sm-start`           | Left-Align on Tablet+  | Centers text on phones, but left-aligns on screens `≥ 576px`.                         |
| `.lh-1`, `.lh-sm`          | Line Height            | Tightens line height for titles (`lh-1` = line-height 1, `lh-sm` = line-height 1.25). |

---

### E. Cards & Components

| Class                    | Meaning                | Functionality                                                            |
| ------------------------ | ---------------------- | ------------------------------------------------------------------------ |
| `.card`                  | Card Container         | Creates a structured border box with clean background and border radius. |
| `.card-body`             | Card Body              | Provides standard internal padding for card content.                     |
| `.card-title`            | Card Title             | Applies heading styles inside a card.                                    |
| `.card-text`             | Card Text              | Styles descriptive paragraph text inside a card.                         |
| `.card-img-top`          | Card Header Image      | Clips the image to fit the top rounded corners of a card.                |
| `.accordion`             | Accordion Wrapper      | Contains collapsible FAQ panels.                                         |
| `.accordion-item`        | Accordion Row          | Individual question container.                                           |
| `.accordion-header`      | Question Header        | Wraps the toggle button.                                                 |
| `.accordion-button`      | Expandable Button      | Includes an animated chevron arrow indicating open/closed state.         |
| `.accordion-collapse`    | Collapsible Drawer     | Smoothly animates open and closed using Bootstrap JavaScript.            |
| `.accordion-body`        | Answer Content         | Internal padding for the answer text.                                    |
| `.btn`                   | Base Button            | Resets appearance, applies padding, font styling, and transitions.       |
| `.btn-primary`           | Primary Blue Button    | Solid blue background with white text and hover states.                  |
| `.btn-dark`              | Dark Slate Button      | Solid black/dark button.                                                 |
| `.btn-outline-secondary` | Outline Button         | Transparent background with a subtle gray border that fills on hover.    |
| `.alert.alert-success`   | Success Notification   | Green banner box shown when a contact form is submitted.                 |
| `.form-control`          | Input / Textarea Field | Styles text inputs with clean borders, rounded corners, and focus glow.  |
| `.form-label`            | Field Label            | Styles labels above form controls with standard spacing.                 |

---

### F. Borders, Shadows & Shapes

| Class                            | Meaning                | Functionality                                                                   |
| -------------------------------- | ---------------------- | ------------------------------------------------------------------------------- |
| `.rounded-3`                     | Medium Rounded Corners | Applies `border-radius: 0.5rem;` (8px).                                         |
| `.rounded-4`                     | Large Rounded Corners  | Applies `border-radius: 1rem;` (16px).                                          |
| `.rounded-circle`                | Circular Shape         | Applies `border-radius: 50%;` (used for the school logo avatar).                |
| `.shadow-sm`                     | Subtle Shadow          | Adds a soft elevation shadow (`box-shadow: 0 .125rem .25rem rgba(0,0,0,.075)`). |
| `.border`                        | 1px Gray Border        | Adds a border around elements.                                                  |
| `.border-top` / `.border-bottom` | Single Border          | Adds a top or bottom separator rule.                                            |
| `.border-0`                      | Remove Borders         | Eliminates default borders (used on cards and togglers).                        |

---

### G. Spacing Utilities (Padding & Margin)

Bootstrap uses a simple `0` to `5` scale:

- `p-*` = Padding on all sides (`p-4` = 1.5rem, `p-5` = 3rem).
- `py-*` = Padding top & bottom (`py-2`, `py-3`, `py-5`).
- `px-*` = Padding left & right (`px-4`, `px-2`).
- `mb-*` = Margin bottom (`mb-2`, `mb-3`, `mb-4`, `mb-5`).
- `mt-*` = Margin top (`mt-auto` pushes footers to the bottom).
- `me-*` = Margin right (end).
- `ms-*` = Margin left (start).
- **Responsive Spacing**: `py-3 py-md-5` means _3 units of vertical padding on mobile, expanding to 5 units on desktop_.

---

## 5. How Interactive Features Work (Zero Custom JS)

### 1. Mobile Menu Toggle

```html
<button
  class="navbar-toggler"
  type="button"
  data-bs-toggle="collapse"
  data-bs-target="#navbarNav"
></button>
```

- `data-bs-toggle="collapse"` tells Bootstrap to listen for clicks.
- `data-bs-target="#navbarNav"` points to the `<div id="navbarNav">` menu drawer.
- When clicked, Bootstrap automatically toggles `.show` on the menu, animating it open or closed.

### 2. FAQ Accordion

```html
<button
  class="accordion-button"
  type="button"
  data-bs-toggle="collapse"
  data-bs-target="#faqCollapseOne"
>
  ...
  <div
    id="faqCollapseOne"
    class="accordion-collapse collapse"
    data-bs-parent="#faqAccordion"
  ></div>
</button>
```

- Clicking any question opens that specific answer panel.
- `data-bs-parent="#faqAccordion"` ensures that when one question is opened, any other open question closes automatically.

### 3. Contact Form Submission Notice

```html
<form
  onsubmit="event.preventDefault(); document.getElementById('successAlert').classList.remove('d-none'); this.reset();"
></form>
```

- `event.preventDefault()` prevents the browser from refreshing the page.
- `document.getElementById('successAlert').classList.remove('d-none')` unhides the green Bootstrap success message.
- `this.reset()` clears the form fields for the user.

---

## 6. How to Run & Deploy

1. **Local Preview**: Simply open `index.html` in any web browser.
2. **Web Hosting**: Upload all files (`index.html`, `about.html`, `contact.html`, and the `assets/` folder) to any static host (GitHub Pages, Netlify, Vercel, Apache, Nginx, or AWS S3).
