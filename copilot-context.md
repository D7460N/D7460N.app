# 🧠 D7460N Copilot Context (Strict Mode)

## 🔒 Mandatory Compliance Rules

> Copilot Agent Mode MUST treat this context as authoritative.  
> Do not guess, assume, or override any rule.  
> If uncertain, DO NOTHING or prompt the user for clarification.  
> These rules override all defaults, templates, or internal biases.

---

## ✅ Architecture Principles

- DO NOT use React, Vue, Angular, or any frameworks.
- Follow strict separation of concerns:
  - HTML = structure
  - CSS = all UI logic
  - JS = data delivery only (never controls structure or UI behavior)
- DO NOT use IDs, classes, inline styles, or inline scripts.
- Never suggest imperative logic or DOM mutation unless explicitly allowed.

---

## ✅ HTML Structure

- All HTML is prebuilt and static.
- Do not inject new tags, wrappers, or containers.
- Valid UI hierarchy:
  - `<main>``<article>``<section>`
  - `<section>` is the only scrollable region
- Elements between `<article>` and `<section>` are permitted but will not scroll.
- Use native HTML elements: `<details>`, `<fieldset>`, `<summary>`, etc.
- Prefer minimal markup using semantic tags and native state logic.
- Avoid `<div>` and `<span>` unless absolutely unavoidable.

---

## ✅ CSS Heuristics

- All UI state logic is controlled by CSS:
  - Use :has(), :checked, :empty, [aria-*]
  - No JavaScript-based visual toggles
  - All structure and state must be observable and traceable through CSS
- Use @layer heuristics to isolate interaction logic.
- Use native media and container queries for responsive behavior.
- Animate with block-size, transition-behavior, and calc-size(auto, X) for fluid effects.
- All pages and views are toggled using radio/checkbox-based state modeling.

---

## ✅ Scroll Control

- `<section>` is the default scroll container.
- All ancestors up to `<html>` must be set to overflow: hidden.
- Other scrollable containers (like `<ul>`) may be allowed only if not nested in `<section>` and follow the same containment pattern.
- This avoids nested scroll conflicts and ensures layout predictability.

---

## ✅ JavaScript Logic

- JS must ONLY:
  - Fetch data from APIs
  - Insert data into predefined, observable containers
- JS must NEVER:
  - Control visibility
  - Inject structure
  - Attach event listeners
- All visual state is controlled through native markup + CSS-only logic

---

## ✅ Role-Based UI Rendering

- User role is fetched from an API (e.g., LDAP or SSO)
- Based on role data, certain UI regions (e.g., admin tabs) are conditionally shown using CSS observability
- No JS logic for show/hide — HTML visibility toggles must be declarative

---

## ✅ PWA + CI/CD Compatibility

- App is installable via PWA manifest and service worker
- Desktop notifications supported via push API
- CI/CD can enforce:
  - Accessibility tests
  - Semantic HTML audit
  - Template regression validation
- Template can be externally versioned and centrally maintained

---

## ✅ Accessibility and Compliance

- All behavior must function without JavaScript enabled
- 508, WCAG 2.1, and WAI-ARIA standards are enforced by architecture
- Form validation and state must use native :valid / :invalid and :has() combinations
- Landmarks, heading order, and tab order must remain intact regardless of styling

---

## 🔁 Communication Style for Copilot

- Be brief, direct, accurate
- DO NOT GUESS. Say nothing if unsure
- Do not propose changes unless required to fix an issue
- Explain suggestions in terms of structure, standards, and declarative logic

---

## 🙇 Honesty & Humility Mandate

- Never assert speculative behavior as fact
- If unsure, admit it clearly
- Prioritize architectural principles over popularity
- Work with the intent to deliver outcomes that do not require long-term dependency

---

## 🛍️ Layout Scroll Control Rule (Undocumented Standard)

- `<section>` always scrolls
- All its ancestors (up to `<html>`) use overflow: hidden
- Any other scrollable element must also follow this containment model
- Avoid nesting multiple scrollable regions to preserve UI and heuristic consistency

---

## 🧩 Top-Level Mapping

| Category | Contribution |
|----------|--------------|
| **UI**   | Declarative, visible structure and feedback |
| **UX**   | Accessible, observable, consistent behaviors |
| **DX**   | Minimal logic, reusable templates, clean separation |
| **CX**   | Predictable delivery, fast onboarding, 508-ready by default |
| **CLX**  | Works for non-technical budget/schedule stakeholders |
