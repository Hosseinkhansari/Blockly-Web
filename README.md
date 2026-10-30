# Blockly Web

A visual page builder: assemble a web page from HTML elements, style it, and see the result live, without writing code.

Live demo: https://hosseinkhansari.github.io/Blockly-Web/

## How to use
1. Pick an element from the toolbar (headings, p, a, div, ul, ol, li, button, `img`).
2. Press + to add it inside the currently selected element. At first, that is the page itself.
3. Click any element in the page to select it. A panel opens under the toolbar.
4. In the panel you can:
   - Styles: background color, padding, size, position, border, font size, flex layout and more
   - Add text: set the text of an element
   - Props: edit attributes such as href and target for links, src and alt for images
   - Delete: remove an element together with its children

## Rules built into the editor
- li can only be added inside ul or ol, and ul and ol accept only li
- Elements like p, headings and img cannot have children
- Style options change per element: text options appear only for elements that hold text, flex options only after display: flex is set

## How it works
- The whole page is stored as a tree object. Each node has an id, type, parentId, children, styles, props and text.
- A recursive function (`buildEl`) rebuilds the page from the tree after every change, and a second recursive function deletes a node with all its descendants.
- The editor is data-driven. The elements and styleFields objects describe each element’s rules and which controls it gets, so adding a new element means adding an object, not new logic.
- The toolbar scrolls horizontally on small screens, and hover effects are disabled on touch devices.

## Built with
HTML, CSS (Grid, Flexbox, CSS variables) and vanilla JavaScript. No libraries.

## Roadmap
- Export the page as an HTML file
- Save the project with LocalStorage
- Undo and redo
- Drag and drop

## Notes
The labels of the style options are in Persian.
