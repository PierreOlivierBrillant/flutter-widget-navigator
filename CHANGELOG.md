# Changelog

## 1.0.1

Two parsing fixes, both reported on real code.

- **Helper methods declared with a concrete widget return type are now followed.**
  `GridView _buttons() {…}` or `Text _title() {…}` were ignored, so their calls
  never appeared in the tree; only `Widget`, `List<Widget>` and
  `PreferredSizeWidget` were recognised. Any capitalised return type that is not
  a known non-widget now counts.
- **`NeverScrollableScrollPhysics()` is no longer listed as a widget.** A
  `ScrollPhysics` suffix rule covers the whole family, and the image providers
  (`AssetImage`, `NetworkImage`, …) were added to the exclusion list.

Also: the repository and issue links in the manifest now point at the renamed
repository.

## 1.0.0

First stable release. Everything below has been in place since the first preview;
this version marks it as ready for daily use.

- `Ctrl+Alt+W` opens the widget tree of the active Dart file in a keyboard-navigable
  list, on the widget nearest the cursor.
- Depth, child count and fold state are spelled out in the item text, so a screen
  reader announces them: `L3 · Padding`, `L2 · Column, 4 children, collapsed`.
- `Alt+Right` / `Alt+Left` expand and collapse; on a leaf, `Alt+Left` moves up to
  the parent widget. `Alt+F1` shows the key list inside the list itself.
- Moving through the list scrolls the editor without touching the cursor. `Enter`
  jumps to the widget, `Escape` leaves everything where it was.
- Helper methods are followed: the contents of `Widget _buildButtons() {…}` appear
  under its call site.
- English and French user interface.

Fixed since the initial preview: the screen reader no longer re-reads the window
title every time an item is collapsed or expanded.

## 0.1.0

First preview.

- `Ctrl+Alt+W` opens the widget tree of the active Dart file in a keyboard-navigable
  list. The list opens on the widget nearest the cursor.
- Depth, child count and fold state are spelled out in the item text, so a screen
  reader announces them: `L3 · Padding`, `L2 · Column, 4 children, collapsed`.
- `Alt+Right` / `Alt+Left` expand and collapse; on a leaf, `Alt+Left` moves up to
  the parent widget.
- `Alt+F1` shows the key list inside the QuickPick itself.
- Moving through the list scrolls the editor without touching the cursor. `Enter`
  jumps to the widget, `Escape` leaves everything where it was.
- Helper methods are followed: the contents of `Widget _buildButtons() {…}` appear
  under its call site.
- English and French user interface.
