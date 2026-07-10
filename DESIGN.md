---
name: AgentHub Direct
colors:
  surface: '#031427'
  surface-dim: '#031427'
  surface-bright: '#2a3a4f'
  surface-container-lowest: '#000f21'
  surface-container-low: '#0b1c30'
  surface-container: '#102034'
  surface-container-high: '#1b2b3f'
  surface-container-highest: '#26364a'
  on-surface: '#d3e4fe'
  on-surface-variant: '#c6c6cd'
  inverse-surface: '#d3e4fe'
  inverse-on-surface: '#213145'
  outline: '#909097'
  outline-variant: '#45464d'
  surface-tint: '#bec6e0'
  primary: '#bec6e0'
  on-primary: '#283044'
  primary-container: '#0f172a'
  on-primary-container: '#798098'
  inverse-primary: '#565e74'
  secondary: '#b9c7e0'
  on-secondary: '#233144'
  secondary-container: '#3c4a5e'
  on-secondary-container: '#abb9d2'
  tertiary: '#4edea3'
  on-tertiary: '#003824'
  tertiary-container: '#001c10'
  on-tertiary-container: '#009365'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#dae2fd'
  primary-fixed-dim: '#bec6e0'
  on-primary-fixed: '#131b2e'
  on-primary-fixed-variant: '#3f465c'
  secondary-fixed: '#d5e3fd'
  secondary-fixed-dim: '#b9c7e0'
  on-secondary-fixed: '#0d1c2f'
  on-secondary-fixed-variant: '#3a485c'
  tertiary-fixed: '#6ffbbe'
  tertiary-fixed-dim: '#4edea3'
  on-tertiary-fixed: '#002113'
  on-tertiary-fixed-variant: '#005236'
  background: '#031427'
  on-background: '#d3e4fe'
  surface-variant: '#26364a'
  success-emerald: '#10b981'
  info-blue: '#3b82f6'
  warning-amber: '#f59e0b'
  error-rose: '#f43f5e'
  fatal-red: '#9f1239'
  slate-50: '#f8fafc'
  slate-100: '#f1f5f9'
  slate-800: '#1e293b'
  slate-900: '#0f172a'
typography:
  headline-lg:
    fontFamily: Inter
    fontSize: 30px
    fontWeight: '700'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-md:
    fontFamily: Inter
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
    letterSpacing: -0.01em
  headline-sm:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '600'
    lineHeight: 28px
  body-lg:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  body-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
  label-md:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.05em
  mono-sm:
    fontFamily: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 18px
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  sidebar-width: 16rem
  gutter: 1rem
  container-padding: 1.5rem
  stack-gap: 1rem
  component-gap: 0.5rem
---

## Brand & Style

The design system is engineered for **AgentHub**, a high-stakes orchestration platform where technical precision meets executive decision-making. The brand personality is **Professional, Technical, and Authoritative**, designed to instill confidence in "Automation Architects" managing mission-critical enterprise processes.

The chosen design style is **Corporate / Modern** with a focus on **Information Density and Functional Clarity**. It prioritizes immediate scannability over decorative elements, utilizing a structured grid and a rigorous semantic color system to transform granular technical logs into actionable business insights. The UI remains lightweight and high-performance by leaning into native browser capabilities (HTML5, Vanilla JS) while maintaining a premium, "Production-Grade" aesthetic.

Key stylistic principles:
- **High Utility:** Every element serves a functional purpose in monitoring or governance.
- **Visual Evidence:** Use of borders and accents to provide clear status mapping.
- **Sober Sophistication:** A neutral Slate foundation that allows the semantic accents (Emerald, Blue, Amber, Rose) to command attention where intervention is required.

## Colors

The color palette is anchored in **Slate** to provide a grounded, technical environment. While the system supports a light mode (`slate-50`), the primary experience is optimized for **Dark Mode** (`slate-900`) to reduce ocular fatigue during long monitoring sessions and emphasize the glowing status indicators.

### Semantic Logic
- **Primary/Neutral:** Utilizes the Slate scale. `slate-900` for backgrounds, `slate-800` for surface containers, and `slate-100` for high-contrast text.
- **Success (ROI/Emerald):** Used for positive growth, completed pipelines, and financial gains.
- **Activity (Blue):** Indicates active processes, informational notices, and system logs.
- **Warning (Amber):** Highlights unexpected but recoverable behaviors or approaching budget limits.
- **Critical/Fatal (Rose/Red):** Reserved for system failures, process terminations, and security alerts. 

In logs, the 8 levels of severity are mapped to specific shades of these colors to ensure "at-a-glance" diagnosis.

## Typography

This design system uses **Inter** for all UI elements to ensure maximum legibility and a neutral, professional tone. For technical data—such as Trace IDs, Inference Costs, and JSON logs—the system falls back to the browser's native **monospace stack** to signal "raw data" to the user.

### Hierarchy Rules
- **Headlines:** Use tighter letter-spacing and bold weights to anchor page sections.
- **Body:** Standardized at 14px (`body-md`) for maximum data density without sacrificing readability.
- **Labels:** Always uppercase with increased letter-spacing when used for status badges or small categories to improve visual distinctness at small sizes.
- **Mobile Scaling:** Headlines above 24px should scale down by 15% on mobile devices to prevent overflow in the 64w-sidebar layout.

## Layout & Spacing

The layout follows a **Fixed Sidebar + Fluid Content** model. 
- **Sidebar:** A fixed `w-64` (16rem) navigation column on the left ensures core architectural navigation is always accessible.
- **Content Area:** A fluid container that uses a 12-column grid for complex data views and a 2x2 grid for the primary Metric Cards.
- **Vertical Rhythm:** A base 4px (0.25rem) spacing unit is used. Standard components use `p-4` (1rem) padding.

### Breakpoints
- **Mobile (< 768px):** The sidebar shifts to a hidden/off-canvas state toggled by a hamburger menu. Metric cards reflow to a single column.
- **Desktop (>= 768px):** The sidebar is fixed. Content uses a max-width of `1440px` to prevent line-lengths from becoming unreadable on ultra-wide monitors.

## Elevation & Depth

The design system uses **Tonal Layers** rather than heavy shadows to maintain a clean, "agentic" feel.

- **Background:** `slate-900` (Dark) or `slate-50` (Light).
- **Cards/Surfaces:** One step lighter/darker than the background with a subtle `shadow-sm` and a `1px` border (`slate-200` in light, `slate-800` in dark).
- **Modals:** Use the native `<dialog>` element. Depth is achieved via a `backdrop-blur-sm` and a `bg-slate-900/50` overlay, effectively separating the orchestration layer from the management layer.
- **Interactive Elements:** Buttons and dropdowns use a slightly more pronounced shadow on hover to indicate tactility.

## Shapes

The system uses a **Rounded** (0.5rem) shape language to soften the industrial nature of the data.

- **Standard Components:** 0.5rem (e.g., Metric Cards, Input fields).
- **Badges/Pills:** Full rounded (`rounded-full`) to clearly distinguish status chips from interactive buttons.
- **Modals:** 0.75rem (`rounded-xl`) to provide a distinct visual container for high-level tasks.
- **Avatars:** Strictly circular to indicate LLM entities (Claude, Gemini) vs. square-ish UI components.

## Components

### Metric Cards
- **Structure:** `bg-white dark:bg-slate-800 p-4 rounded-lg shadow-sm border-l-4`.
- **Acent Color:** The left border color MUST match the semantic role (Emerald for ROI, Blue for Activity).

### Status Badges
- **Style:** Small, uppercase text with `rounded-full`. 
- **Variants:** Success (Emerald), Alert (Rose), Warning (Amber), Info (Blue).

### Sidebar
- **Fixed width:** `w-64`. 
- **Styling:** `bg-slate-50 dark:bg-slate-900 border-r border-slate-200 dark:border-slate-800`.
- **Active State:** Navigation links should use a subtle background highlight and a primary-color left indicator.

### Modals (<dialog>)
- Use the native HTML5 `<dialog>` element.
- **Backdrop:** `backdrop:bg-slate-900/60 backdrop-blur-sm`.
- **Close Logic:** Must support native ESC key behavior and a "Cancel" button that calls `dialog.close()`.

### Tables & Lists
- **Rows:** Hover state should change background to `slate-100` (light) or `slate-800` (dark).
- **Actions:** Hidden by default, revealed on hover or via a persistent "three-dots" icon using the `Action Dropdown` pattern.

### Pipeline Steps
- Vertical layout connected by a `border-l-2 border-slate-300 dark:border-slate-700` line.
- Each step is a card with a specific tool-calling badge (e.g., "MuleRun", "n8n").

### Toggles (Human-in-the-loop)
- **State:** `bg-slate-300` for off, `bg-emerald-500` for on.
- **Animation:** Smooth `transition-colors` with a white circular slider.