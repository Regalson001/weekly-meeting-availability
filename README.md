# Weekly Meeting Availability Schedule

> A fully accessible, semantic HTML5 and modern CSS3 application designed to track and visualize team meeting availability across days and time slots. Built with a strong emphasis on web accessibility standards, CSS custom property design systems, and responsive layouts.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Key Features & Architecture](#key-features--architecture)
3. [Accessibility (a11y) Compliance](#accessibility-a11y-compliance)
4. [Design System & CSS Custom Properties](#design-system--css-custom-properties)
5. [Getting Started & Local Installation](#getting-started--local-installation)
6. [Testing & Quality Assurance](#testing--quality-assurance)
7. [Future Roadmap](#future-roadmap)
8. [License](#license)

---

## 1. Project Overview

The **Weekly Meeting Availability Schedule** is a web-based utility designed to streamline coordination across remote or hybrid teams. In fast-paced software development environments, visualizing team bandwidth at a glance is critical for scheduling alignments. 

This project bridges clean semantic markup with advanced CSS styling techniques, fulfilling strict test criteria including custom variable-driven color mapping, semantic row/column scoping, and screen-reader-optimized attributes.

---

## 2. Key Features & Architecture

* **Semantic Table Markup**: Structured using native HTML5 table elements (`<table>`, `<caption>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, and `<td>`) to ensure proper document outline and parser behavior.
* **Dynamic Availability Mapping**: Data cells are categorized via dedicated classes (`.available-0` through `.available-5`) to reflect precise headcount availability metrics.
* **Interactive Legend Component**: Features a dedicated legend container (`#legend`) paired with a custom linear-gradient indicator (`#legend-gradient`) utilizing hard-line color stops for clear visual separation of tiers.
* **Alternating Row Styling**: Employs distinct row wrapper classes (`.sharp` and `.half`) to apply structured, alternating border rules (`--solid-border` vs. `--dashed-border`).

---

## 3. Accessibility (a11y) Compliance

Accessibility is a primary pillar of this project, ensuring users utilizing assistive technologies (such as screen readers) experience seamless navigation:
* **Explicit Scope Attributes**: All column headers (`<th>` in the header row) include `scope="col"`, while row time headers include `scope="row"` to explicitly declare data relationships for tabular data cells.
* **Descriptive Aria Labels**: Because data cells rely on background color coding for visual status, every availability cell incorporates an explicit `aria-label` attribute (e.g., `aria-label="0 available"`, `aria-label="5+ available"`), ensuring complete context for non-visual users.

---

## 4. Design System & CSS Custom Properties

The project utilizes a centralized configuration pattern managed inside the CSS `:root` scope, maintaining design token consistency:

```css
:root {
  --color0: #ff4d4d;      /* 0 people available */
  --color1: #ffa64d;      /* 1 person available */
  --color2: #ffff4d;      /* 2 people available */
  --color3: #a6ff4d;      /* 3 people available */
  --color4: #4dffa6;      /* 4 people available */
  --color5: #4d4dff;      /* 5+ people available */
  --solid-border: 2px solid #333;
  --dashed-border: 2px dashed #333;
}
