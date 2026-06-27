# Apparatus

A macOS scholarly workbench for EU law PhD research. Apparatus combines a case law library, document viewer, annotation system, and OSCOLA citation generator into a single native app — built for researchers who live inside CJEU judgments.

---

## What it does

Apparatus is organised around four modes, accessible from the sidebar:

| Mode | Purpose |
|---|---|
| **Search** | Find cases from EUR-Lex / CELLAR by C-number, T-number, or case name |
| **Library** | Browse and manage your case law collection and literature references |
| **Annotations** | Mark up documents and review your annotations across all cases |
| **Writing** | *(coming soon)* Draft and export thesis chapters |

---

## Getting started

### 1. Set your research interest

Open **Settings → Research interest** and select your area: Direct Taxation, Indirect Taxation, State Aid, Competition Law, or Other. Apparatus pre-loads a curated starter set of tags matched to your field. You can always add, rename, or delete tags from the **Tags** menu in the menu bar.

### 2. Choose a documents folder

Open **Settings → Case documents folder** and choose where Apparatus should save downloaded HTML and PDF files. The default is `~/Documents/Apparatus Cases`. Files are organised automatically into subfolders by case number (e.g. `C-168-01/judgment.html`). The SQLite database stays in the app container and is managed automatically.

### 3. Search for cases

Use the search bar at the top of the window to find cases by C-number or T-number (e.g. `C-446/03`). Results show the judgment, AG Opinion, and any orders for that case. Click **Add to Library** to save a case — Apparatus downloads the HTML and PDF from CELLAR in the background.

If a case is not available via EUR-Lex, use **Library → Add case manually** to enter the details by hand and attach a local PDF.

---

## The Library

The Library organises your cases into four columns: **Judgments**, **AG Opinions**, **Orders**, and **Literature**. Use the checkboxes in the strip at the top to show or hide columns.

### Working with cases

- **Hover** over a case card to reveal quick-action buttons: annotate (pencil), info (ⓘ), and delete (trash).
- **Right-click** for the same options as a context menu.
- **Click the ⓘ button** to open the detail inspector, which shows OSCOLA citations (bibliography and footnote), CELEX, ECLI, court formation, procedure type, subject matters, and file status (PDF / HTML).
- **Click the pencil button** to open the case in the reading workspace for annotation.

### File pills

Each card shows PDF and HTML pills. A coloured pill means the file is available locally; a grey pill with a slash means it hasn't been downloaded yet. Open the inspector and click **Retry download** to try again, or **Attach** to link a local file manually.

### Literature

Literature references extracted from cases appear in the Literature column. Each article card shows the author, citation, and source case. Hover to reveal attach (paperclip) and delete (trash) buttons. Use **Select all** / **Deselect all** in the column header to bulk-select, then **Delete N** to remove multiple articles at once.

---

## Annotations

### Mark up

Open any case from the Library to enter the three-panel reading workspace:

- **Left panel** — your case list, filtered to the current document type.
- **Centre panel** — the document viewer (HTML or PDF).
- **Right panel** — the annotation draft form and your existing annotations for this case.

To create an annotation, fill in the fields on the right:

| Field | Purpose |
|---|---|
| **Description** | A short label you write — used as the card title in Review |
| **Snippet** | A verbatim quote from the judgment |
| **Reference** | Page or paragraph number (appended to the footnote citation) |
| **Comment** | Your own analysis or note |
| **Tags** | Select from your tag library |
| **Linked cases** | Cross-references to related C-numbers |

The **footnote** field is pre-filled with the OSCOLA footnote citation for the case. The full bibliography citation is generated automatically.

Click **Save annotation** to store it. Saved annotations appear below the form and can be clicked to begin editing.

### Review

Switch to the **Review** tab to see all your annotations as cards across all cases, or filter by case and tag using the controls at the top.

Each card shows the case reference, annotation date, your description, and up to three tag pills. **Click** a card to expand it and see the full snippet, comment, all tags, linked cases, and the OSCOLA citation block ready to copy into your thesis.

Hover over a card to reveal the action toolbar (top-right corner):

| Icon | Action |
|---|---|
| **chevron** | Expand / collapse the card |
| **pencil** | Jump back to Mark up for this case |
| **trash** | Delete the annotation (with confirmation) |

Right-click any card for the same options as a context menu.

---

## Tags

Open **Tags → Manage Tags…** (or press **⌘⇧T**) to manage your tag library. Tags are grouped by dimension (Legal basis, Concept, and any legacy dimensions). From this panel you can:

- **Add** a new tag by clicking **New tag**, entering a label, and choosing a dimension.
- **Rename** any tag by clicking the pencil icon next to it.
- **Delete** any tag that is not currently assigned to an annotation.

Tags assigned to existing annotations are marked **in use** and cannot be deleted — this protects your annotation data.

---

## OSCOLA citations

Apparatus generates OSCOLA citations automatically for every case in your library.

- **Bibliography**: `Case C-446/03 Marks & Spencer plc v David Halsey (Her Majesty's Inspector of Taxes) [2005] ECR I-10837`
- **Footnote**: `Case C-446/03 Marks & Spencer [2005] ECR I-10837, para 45`

The footnote is pre-filled into new annotations. If you add a paragraph reference in the **Reference** field, it is appended automatically. Both forms are available as selectable text in the annotation cards and the case inspector, ready to paste directly into your thesis.

---

## File organisation

```
~/Documents/Apparatus Cases/        ← your chosen documents root
  C-446-03/
    judgment.html
    judgment.pdf
  C-168-01/
    judgment.html
    opinion.html
  literature/
    {id}/
      article.pdf
```

Case folders use the C- or T-number with slashes replaced by hyphens. Document filenames follow the type: `judgment`, `opinion`, `order`, `ruling`. Apparatus keeps files on disk in sync with the database — deleting a case from the Library removes its files from the folder automatically.

---

## Settings

| Setting | Description |
|---|---|
| **Research interest** | Pre-loads a starter tag set for your field |
| **Case documents folder** | Where HTML and PDF files are saved; can be changed at any time without moving existing files |
| **Database** | Fixed in the app container (`~/Library/Application Support/apparatus/`); managed automatically |

---

## Requirements

- macOS 26 or later
- An internet connection for EUR-Lex / CELLAR downloads

---

## Notes

- Apparatus does not require a login or API key. It queries EUR-Lex and CELLAR directly using public endpoints.
- All data is stored locally. Nothing is uploaded to any server.
- The database is a plain SQLite file. Advanced users can open it with any SQLite browser.
