# Accessibility
Some tips to improve website accessibility

## Breadcrumb-Navigation 

**When to use:**
- Websites that have hierarchical structure with categories > subcategories > product pages. Breadcrumb navigation can assist users in finding their way back to higher-level pages, sections, categories, or topics 
  - E-commerce websites
- Websites that have a large amount of content
  - News portals
  - Blogs
  - Educational websites
- Websites with sequential processes or workflows. Breadcrumb navigation can indicate the progress made and remaining steps
  - Online banking
  - Travel booking
  - Job application platforms

**When not to use:**
- Single level websites with no logical hierarchy
- Sites with clear and concise main navigation, in this case breadcrumb navigation is redundant and adds unnecessary complexity

---

## Search Fields
- Clickable labels
   - upon clicking on labels, the input field will be focus
- `<input type=”search”>` search type attribute to semantically mark a search field
- `autocomplete` supports users with concentration difficulties
- `autofocus` set the cursor directly inside the search field when the page loads

---

## Filter options
- `<fieldset>`
  - to ensure that assistive technologies interpret a group of filter options as a related set
- `<legend>`
  - to label the group

<code>Example:</code>

     <fieldset>
        <legend class="sr-only">Nachrichteneingang filtern</legend>
        <label for="inbox-search">Suche</label>
        <input type="text" name="inbox-search" id="inbox-search" value="">
     </fieldset>


---

## Pagination

**When to use:**
- Large datasets
  - When the table contains a large number of rows that cannot be efficiently displayed in a single page, pagination can help prevent overwhelming the UI
- Performance concerns
  - Loading and rendering large datasets can impact performance. Pagination allows for loading and displaying smaller subsets of data, improving performance
- Usability and readability
    - When the table has many rows, pagination enhances readability by limiting the number of records displayed per page.
    - Reduces cognitive load
    - User can easier navigate and locate specific information

**When to consider alternatives**
- Small dataset
- Instant data access 
   - Pagination may not be necessary when the table contains built-in filters for each column

## Extensive List Elements
- `aria-label`
  - provides a text alternative for an element
  - allows developers to specify a descriptive label that can be read by assistive technologies such as screen readers
   - Useful scenarios
     - providing a label for form controls, such as buttons or input fields, that have no visible text.
     - describing the purpose of icons or graphical elements that do not have accompanying text.
- `aria-describedby`
  - lists the ids of the elements that describe the object
  - used to establish a relationship between widgets or groups and the text that describes them
  - Useful scenarios
    - providing a more detailed description or instructions for a form field.
    - linking an error message to an input field to explain why the input is invalid

---

## Pop-up Menus

- `aria-expanded` true | false
  - ensures that a screen reader can recognize if a pop-up menu is expanded or collapsed
- `aria-haspopup="true"`
  - ensures that a screen reader can identify if an element is an expandable menu that overlays other content when expanded
- `aria-hidden`
   - hides content from assistive technology but doesn't visually hide anything
   - ⚠️ `aria-hidden="true"` should **not** be used on focusable elements⚠️

---

## Tables
- `<table>`
  - to ensure that a screen reader recognizes an element as a table, it should be wrapped in a `<table>` tag
- `<caption>`
  - providing a caption generates table heading that is read out to a screen reader when they navigate directly to a table using a keyboard shortcut
- `<thead>`
  - used to create a group of column headers
- `<tbody>`
  - groups the table content into rows and cells
- `<th>`
  - defines header cell
- `scope` col | row
  - attr of `<th>` that informs screen reader whether it is a column or a row



References:

 https://www.heise.de/hintergrund/Accessibility-im-Web-Teil-2-Barrierefreie-Inhalte-7467924.html?seite=1
