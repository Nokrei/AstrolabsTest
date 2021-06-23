# AstrolabsTest
### About
Landing page for Astrolabs. Made with the use of HTML, CSS, JS. Elements of styling made with Bootstrap and SASS. 
### Structure
- All content in the body is divided into sections, and then further split into articles and divs. 
- Each section has a corresponding CSS file.
- When wanting to check / change style for a specific element, i.e. instructor description in the instructors section, the style assigned to that element
can be found in /styles/instructors.css .
- Global styles are stored in the /styles/main.css file and contain a number of variables, classes applied, backgrounds, box-shadows and so on.
- Overrides to Bootstrap are stored in /styles/custom.scss - SASS is compiled to custom.css and custom.css.map by Live Sass Compiler (VS code extension).
- All visual assets are stored in the /images folder, where they are further sorted into categories.
- Font used in the App - Brown Bold - can be found in the /fonts folder.
### Styling
- BEM convention is followed for naming classes, although not strictly. 
- Bootstrap handles most of the responsiveness rather well.
- Media queries added for max-width 800px for now where applicable.
- The general look of the App seams to be too bright and lacking contrast between elements - colors taken from Figma design.
### JavaScript
- Navigation Bar transition to Hamburger Menu handled by Bootstrap
- Navigation Bar made to stick to the top of the page when scrolling achieved by vanilla JS - `script` located under `nav` section
- `script` for dynamic handling of days left till next course can be found under the `.intro` section. It compares the current day `currentDay` and current month `currentMonth`
  with the values in `.daysLeft`. The `monthList` array of objects contains a list of all the months and their lengths. The comparison of `month` and `currentMonth`
  despite them being different types (string and number) is enabled by a `.map` function. 
  An if / else chain sets the `innerHTML` of `.daysLeft` accordingly and provides three potential outcomes: 
  - display days left till the course if it starts this month or the next (takes into account varying month lengths, but not leap years)
  - if the course starts in the month following the next one (i.e. next month is Jul and course starts in Aug): display 'More than a month.'
  - if the starting date of the course is in the past: display 'Already Started?'
- Alumni section made interactive with vanilla JS - `script` can be found inside the `.alumni` section. All the alumni along with relevant information are stored in the
  `testimonialArr` array of objects. 
  - Initially the 'middle' of the array populates the relevant div's innerHTML. 
  - Upon user selection of radio button an `onclick` event is executed that triggers `change` and `addAnim` functions which set the innerHTML accordingly and start a fade in animation. 
  - Upon mouse leave of the radio button area, the `removeAnim` function is executed which removes the animated class from the divs so that it can be re-applied on next click.
- Carousel in .promo section implemented using Glide JS. Very easy to work with and straightforward configuration. Had some issues finding the right CDN to link the script and 
  styling, as they cannot be read from node_modules
- Accordion in .FAQ section and modals handled by Bootstrap. Modals scaled down on mobile with CSS transform.


