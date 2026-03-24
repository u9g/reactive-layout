# Changelog

## 1.0.2

- Dragged tabs now show a full-size ghost image anchored to the cursor's top-left corner, instead of the browser's default drag preview.

## 1.0.1

- Added npm badges and links to live demo, npm, and GitHub in README.

## 1.0.0

- Initial release.
- Split panes with recursive nesting.
- Draggable tabs between panels with reordering.
- Drop on panel edges to split horizontally or vertically.
- Resizable panes with 5% minimum size.
- Optional localStorage persistence with debounced saves.
- SSR-safe (no window/localStorage access during server render).
- App-specific panel content and tab icons via provide/inject.
