# ♿ Accessibility Audit Report — Week 2

**Project:** Multi-Page Portfolio Structure  
**Student:** Francis Osoro  
**Date:** June 19, 2026  

---

## 🔍 Overview of Initial Issues Found
During the initial structure review of the project files, several critical accessibility and validation barriers were identified:

1. **Missing Language Attribute:** The baseline HTML structure lacked the `lang="en"` attribute within the `<html>` tag, preventing screen readers from identifying the primary language of the document.
2. **Non-Semantic Elements (div-itis):** Core sections like the navigation, header, sidebar, and footer were constructed entirely out of generic `<div>` blocks, hiding the page layout architecture from assistive tools.
3. **Implicit Form Elements:** Labels in the contact section were not programmatically linked to their corresponding inputs via `for` and `id` pairings.
4. **Missing Graphic Descriptions:** Placeholders lacked descriptive `alt` attributes, making the visual data completely empty for visually impaired users.

---

## 🛠️ Remediations & Fixes Implemented

### 1. Semantic Elements & Document Architecture
- Converted all layout-blocking generic `<div>` tags into explicit landmark segments: `<header>`, `<nav>`, `<main>`, `<article>`, `<aside>`, and `<footer>`.
- Implemented a proper nested heading hierarchy beginning strictly with an `<h1>` for the primary context locator and descending sequentially (`<h2>` -> `<h3>`) without skipping levels.

### 2. Form Control Binding
- Refactored the interactive elements in `contact.html` to enclose inputs inside `<fieldset>` and `<legend>` blocks for contextual group descriptions.
- Bound all form elements programmatically:
  ```html
  <label for="fullname">Full Name:</label>
  <input type="text" id="fullname" required>