// PROMPT 1: Initialization & Setup
Read PROJECT_REQUIREMENTS.md. Initialize a new React project using Vite in the current directory. Install Tailwind CSS, framer-motion, react-router-dom, and lucide-react. Configure Tailwind properly. Create a basic App.jsx with React Router set up for the '/' and '/generator' routes. 

// PROMPT 2: The Animated Bento Landing Page
Build the Landing Page component for the '/' route. Implement a responsive CSS Grid "Bento Box" layout. Use framer-motion to add a staggered entrance animation to the bento cards when the page loads. Include a primary bento card with a call-to-action button that navigates to the '/generator' route. Keep the styling clean and professional, utilizing Malek Property Solutions' brand colors (light blue and slate).

// PROMPT 3: Generator State & Base UI
Move to the Generator page. Build the base UI. Create a state object for the Header Inputs (TO, Address, Date, Work Order #) and an array of objects in state for the Bid Table rows based on the columns defined in the requirements. Build the visual layout with inputs for the header, and a mapped table for the rows. Ensure the "Amount" column strictly calculates `Qty * Price` and the table footer shows the total sum. Add buttons to "Add Row" and "Remove Row".

// PROMPT 4: LocalStorage & Autocomplete Integration
Implement the Line Item Library logic. Create a custom hook or utility to manage saving to and reading from `localStorage`. Modify the "Description" column input to be an autocomplete combobox. When the user types, show a dropdown of matching items from local storage. When a saved item is clicked, automatically populate the corresponding Scope, Details, Unit, and Price fields for that specific row. Ensure new unique line items are saved to local storage when the form updates. To test this, pre-populate local storage with a mock item: { description: "Lockbox Installation", scope: "Install new lockbox on front door", details: "Code: 1601", unit: "EA", price: 45 }.

// PROMPT 5: Print Layout & Polish
Implement the Print functionality. Add a primary "Print/Save PDF" button. Go through every component on the Generator page and add Tailwind `print:*` utility classes. When printing: hide all action buttons, hide the autocomplete dropdown arrows, remove the borders from input fields so they look like standard text, and ensure the business header (Company Name, Contact, Address) is prominently displayed and formatted like a professional invoice. Ensure the layout fits well on standard Letter/A4 paper sizes.
