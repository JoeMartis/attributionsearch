# Module Attribution Search

A single-file, searchable directory of citations and attributions for course
materials. Drop in your records and your course name and you get a filterable,
accessible web page — no build step and no dependencies.

## Quick start

1. Open `index.html` and set your course name in the two spots near the top:
   - the `<title>` tag, and
   - the `<b>Your Course Name</b>` text in the header.
2. Add your records to the `RAW_RECORDS` array in the `<script>` block
   (see [Adding records](#adding-records)).
3. Open `index.html` in a browser — or host it. Because the file is named
   `index.html`, GitHub Pages will serve it from the repository root
   automatically.

## Adding records

`RAW_RECORDS` is a list of objects, one per attributed item:

```js
{
  id: `1`,
  name: `Cartoon businesspeople illustration`,
  location: `CS101.Module1`,
  unit: `L1.1; L1.2; L3.10`,
  lecture: `Introduction to the Course`,
  citation: `Ai Generated, Group, Team image by ghasoub via Pixabay`
}
```

| Field      | Purpose                                                  |
| ---------- | -------------------------------------------------------- |
| `id`       | Unique identifier (string).                              |
| `name`     | Short description of the item being attributed.          |
| `location` | Where the item lives (e.g. a course or module code).     |
| `unit`     | One or more units. Separate multiple with `; `.          |
| `lecture`  | One or more videos/lectures. Separate multiple with `; `.|
| `citation` | The full citation / attribution text.                    |

### Items in multiple units or videos

If an item appears in several units or videos, list them in a single field
separated by `; `:

```js
unit: `L1.1; L1.2; L3.10`,
```

The page splits these apart automatically, so each value gets its own entry in
the filter dropdowns and the item appears whenever **any** of its units or
videos is selected. (Without this, an item would only be found by typing into
the search bar.)

## Features

- Full-text search across every field — name, location, unit, lecture, citation.
- Two dropdown filters (by unit and by video/lecture), with options sorted
  numerically so `L3.10` follows `L3.9` instead of `L3.1`.
- A "Clear All Filters" button.
- Responsive layout, automatic dark mode, and accessibility support
  (skip link, ARIA live regions, reduced-motion handling).

## Files

- `index.html` — the entire app: HTML, CSS, and JavaScript in one self-contained file.
