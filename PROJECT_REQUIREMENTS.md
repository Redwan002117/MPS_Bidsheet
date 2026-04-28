# App Name: MPS Bid Generator
# Tech Stack: React (Vite), Tailwind CSS, Framer Motion (for animations), React Router DOM, Lucide React (for icons).

## Business Details (For Header/Print Layout)
* **Company Name:** Malek Property Solutions LLC
* **Contact Number:** +1(507) 619-5086
* **Email:** maleksolutionllc@gmail.com
* **Address:** 18040 Gleaming CT. Lakeville, MN 55044
* **Brand Colors:** Light blue, white, and slate/gray. 

## Application Architecture
The app consists of two main routes:
1.  **Landing Page (`/`)**: A modern dashboard utilizing an animated bento-box grid layout. 
2.  **Generator Page (`/generator`)**: The core tool for creating, auto-filling, and printing bids.

## Feature Specifications

### 1. The Landing Page (Bento Layout)
* Use `framer-motion` to create a staggering fade-in effect for the bento boxes.
* **Bento Grid Structure:**
    * A large hero box welcoming the user to the MPS Bid Generator with a "Create New Bid" CTA button.
    * A box highlighting "Quick Stats" (e.g., number of saved line items in local storage).
    * A box highlighting common property preservation categories (e.g., Winterization, Lawn Care, Lockbox Management).
    * The layout should be responsive (stack on mobile, grid on desktop).

### 2. The Generator Page
**Header Inputs (Client Info):**
* TO (Text input)
* Address (Text input)
* Date (Date picker, default to today)
* Work Order # (Text input)

**Dynamic Bid Table Columns:**
* Description (Searchable Autocomplete/Combobox)
* Scope (Text input)
* Details (Text input)
* Qty (Number input)
* Unit (Text input - e.g., EA, CY, SQFT)
* Price (Number input)
* Amount (Read-only, auto-calculated: Qty * Price)

**Table Logic:**
* Users can "Add Row" and "Delete Row".
* A "Total Amount" row at the bottom must automatically sum all individual row amounts.

### 3. Line Item Library (LocalStorage Autocomplete)
* The app must maintain an array of `savedItems` in the browser's `localStorage`.
* Whenever a user adds a new item to the table and fills it out, it should seamlessly save to this library (ignoring exact duplicates).
* The "Description" column must act as an autocomplete dropdown. When a user types (e.g., "Lockbox"), it suggests matches from `localStorage`.
* Selecting a suggestion auto-fills the Scope, Details, Unit, and Price for that specific row (e.g., auto-filling a lockbox code to 1601 if saved previously).

### 4. Print & Download Logic
* Rely on `window.print()` and Tailwind `@media print` utilities.
* **Print View:** When printing, hide all UI buttons ("Add Row", "Print Bid", navigation), hide dropdown arrows, remove input borders, and render the inputs as flat text. The output must perfectly resemble a formal corporate document matching the provided business details.
