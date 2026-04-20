# DDIA-knowledge-graph

An interactive knowledge graph of **Designing Data-Intensive Applications** by Martin Kleppmann.
198 hand-authored concepts across all 12 chapters. Search, click, explore.

**🔗 Live demo:** https://sugun-ravipalli.github.io/DDIA-knowledge-graph/
*(Available once you enable GitHub Pages — see [Deploy to GitHub Pages](#deploy-to-github-pages).)*

---

## Why this exists

I tried to read DDIA several times and kept bouncing off. It's a dense book — every chapter introduces a dozen ideas that reference other chapters, and linear reading made the cross-connections impossible to hold in my head.

So I turned the book into a graph. Every concept is a node. Every "A is related to B" is an edge. I can now search "Reliability" and see, at a glance, every chapter and concept it touches — which is how my brain actually wants to learn this stuff.

If you've also found DDIA intimidating, maybe this helps you too.

---

## What's inside

- **395 nodes:** 1 book → 3 parts → 12 chapters → 54 sections → 127 subsections → **198 concepts**
- **1,255 edges:** structural containment, primary coverage, related-concepts, and cross-chapter "also appears in"
- **Every node has a description.** Chapters have 4-5 sentence summaries. Concepts have 2-4 sentence explanations written from the book. Sections carry snippets from the PDF.
- **Reading-order labels:** concepts are numbered `[Ch.N·NN]` — `[Ch.1·02] Reliability` is the second concept of Chapter 1. Follow the numbers to read the book in order.
- **Single-file HTML.** No install, no server, no dependencies beyond D3 from a CDN.

## How to use it

1. Open the live demo (or `index.html`) in any modern browser.
2. **Search** any term in the top bar — `reliability`, `consensus`, `lsm-tree`, even `Ch.9·03`.
3. **Click** a node to see its description, parent chapter, related concepts, and every other chapter it appears in.
4. **Drag** any node to move it. It stays where you drop it (sticky layout). Double-click a pinned node to release it.
5. Use the sliders in the top-right corner to tune **Repulsion**, **Link length**, **Collision**, **Gravity**, and **Labels**. `Pin all` / `Release all` to freeze or unfreeze the layout. `Reheat` to kickstart the simulation.

### Suggested learning workflow

1. **Reset.** Click the chapter node you want to start with — read its summary in the right panel.
2. **Start at `·01`** of that chapter (search `Ch.1·01`). Work through the concepts in numbered order.
3. **Follow the related-concept links** in each card when something cross-references another chapter — that's exactly when the book starts making its subtle connections.
4. **Pin the concepts you already understand.** The graph becomes a map of what you've learned.

---

## Deploy to GitHub Pages

You need about five minutes.

```bash
# 1. Create the public GitHub repo (already done):
#    https://github.com/Sugun-ravipalli/DDIA-knowledge-graph

# 2. From this directory on your machine:
git init
git add .
git commit -m "Initial commit: DDIA knowledge graph"
git branch -M main
git remote add origin https://github.com/Sugun-ravipalli/DDIA-knowledge-graph.git
git push -u origin main

# 3. Enable GitHub Pages:
#    GitHub repo → Settings → Pages →
#    Source: "Deploy from a branch"
#    Branch: main / root
#    Save

# 4. Wait 1-2 minutes. Live URL:
#    https://sugun-ravipalli.github.io/DDIA-knowledge-graph/
```

The `.nojekyll` file in the root tells Pages to serve the HTML as-is (no Jekyll build step).

---

## Build it yourself (for a different book)

The graph was generated from the DDIA PDF using a small Python pipeline. The approach is reusable for any book with a clean table of contents.

Rough recipe:

```python
import pymupdf

# 1. Extract the table of contents — every heading becomes a node.
d = pymupdf.open("your-book.pdf")
toc = d.get_toc()   # [[level, title, page], ...]

# 2. For each section, extract a text snippet from its pages.
#    (First ~400 chars makes a decent description.)

# 3. Hand-author a concept library — a list of
#    (name, description, chapter_id, aliases, related_names) tuples.
#    ~15-20 concepts per chapter, 2-4 sentence descriptions.
#    This is the labour-intensive step, and also the valuable one.

# 4. Build nodes + edges:
#    - containment edges (book → part → chapter → section → subsection)
#    - primary edges (concept → its home chapter)
#    - related edges (concept ↔ concept, from your library)
#    - mentioned_in edges (concept → other chapters, by alias matching)

# 5. Serialize to JSON, inline into the HTML template (see index.html's <script>),
#    ship as a single file.
```

If there's interest I'll extract this into a proper CLI. File an issue.

---

## Roadmap

- [ ] Deeper pass: expand from 198 to ~400 concepts with worked examples per concept
- [ ] Export as Obsidian vault (folder of linked `.md` files)
- [ ] Export as Neo4j CSV + Cypher import script
- [ ] Generate quiz questions per chapter (flashcard mode)
- [ ] Port the pipeline to other books (*Database Internals*, *Data Pipelines Pocket Reference*, …)

---

## Credits

- Concepts, chapter outline, and inspiration: **Martin Kleppmann**, *[Designing Data-Intensive Applications](https://dataintensive.net/)* (O'Reilly, 2017). This graph is a study aid; it doesn't include the book's text. If you haven't, buy the book.
- Graph rendering: [D3.js](https://d3js.org/) v7.
- Built by **Sai Sugun**.

## License

MIT. See [LICENSE](LICENSE).
