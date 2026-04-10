## Outline Views

An outline view presents hierarchical data as a scrollable list of cells arranged into rows and columns.

At minimum, an outline view has one column holding the primary hierarchy — parent containers and their children — and can include additional columns for supplementary attributes such as size or modification date. Parents show disclosure triangles that expand to reveal their children. The Finder uses an outline view for navigating the file system.

## Best Practices

Outline views are best suited to text-based content and are commonly placed on the leading side of a split view, with related detail on the opposite side.

**Use a table rather than an outline view for non-hierarchical data.**

**Show the hierarchy in the first column only.** Let subsequent columns display attributes that apply to the hierarchical items in the primary column.

**Give each column a descriptive heading.** Use short nouns or noun phrases with title-style capitalization, no trailing punctuation, and no trailing colon. Always include column headings in a multi-column outline view; for a single-column view without a heading, provide context through a label or surrounding UI.

**Consider supporting sort-by-column.** Let people click a column heading to sort ascending or descending by that column, with optional secondary sorts applied behind the scenes. When the primary column is sorted, sort at each level of the hierarchy (e.g., top-level folders first, then items within each folder). Clicking a sorted column again should reverse the direction.

**Let people resize columns.** Row data varies in width, so users need to widen columns to reveal content that would otherwise be clipped.

**Make expanding and collapsing nested containers easy.** Clicking a disclosure triangle should expand just that container; Option-clicking should expand all descendants (as the Finder does).

**Persist expansion state.** When someone drills into several levels to reach an item, remember that state so they don't have to repeat the navigation next time.

**Consider alternating row colors in multi-column outline views.** Striping helps the eye track row values across columns, especially in wide views.

**Allow inline editing where it makes sense.** Users expect a single click on an editable cell to begin editing its contents. Double-click can be mapped to a different action (for example, single-click to rename a file, double-click to open it). Reordering, adding, and removing rows are also useful when appropriate.

**Prefer a middle ellipsis over end-clipping when truncating cell text.** Keeping both the beginning and end of the text visible makes entries easier to distinguish.

**Provide a search field for long outline views.** Windows whose primary content is an outline view commonly place a search field in the toolbar.
