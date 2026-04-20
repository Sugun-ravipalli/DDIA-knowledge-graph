# DDIA Knowledge Graph

An interactive knowledge graph of **Designing Data-Intensive Applications** by Martin Kleppmann — 198 hand-authored concepts across all 12 chapters, fully searchable and navigable.

**🔗 Live: [sugun-ravipalli.github.io/DDIA-knowledge-graph](https://sugun-ravipalli.github.io/DDIA-knowledge-graph/)**

---

## Why

DDIA is a book where Chapter 5 quietly depends on ideas from Chapter 9, and Chapter 7 casually reuses something from Chapter 2. Linear reading makes you carry that whole web in working memory.

I turned it into a graph instead. Every concept is a node, every cross-reference is an edge. Click "Reliability" and you can *see* — at a glance — every chapter and concept it touches.

If you've also bounced off DDIA, maybe this helps.

---

## What's inside

- **395 nodes** — 1 book → 3 parts → 12 chapters → 54 sections → 127 subsections → 198 concepts
- **1,255 edges** — structural containment, primary coverage, related concepts, cross-chapter mentions
- **Every node has a description** — 4–5 sentence chapter summaries and 2–4 sentence concept explanations, all original paraphrasing (the book's text is not included)
- **Reading-order labels** — concepts are numbered `[Ch.N·NN]`; follow the numbers to read the book in order
- **Single-file HTML** — no install, no server, just D3 from a CDN

## Using it

1. Open the [live site](https://sugun-ravipalli.github.io/DDIA-knowledge-graph/) (or `index.html` locally).
2. **Search** any term — `reliability`, `consensus`, `lsm-tree`, or `Ch.9·03`.
3. **Click** a node to see its description, parent chapter, related concepts, and every other chapter it appears in.
4. **Drag** to pin. Double-click to release. Sliders in the top-right tune repulsion, link length, collision, gravity, and label density.

### Suggested workflow

1. Click the chapter node you want to start with — read the summary.
2. Search `Ch.N·01` and work through concepts in numbered order.
3. Follow the related-concept links in each card — that's where the book's subtle cross-references live.
4. Pin the concepts you understand. The graph becomes a map of what you've learned.

---

## Run locally

```bash
git clone https://github.com/Sugun-ravipalli/DDIA-knowledge-graph.git
cd DDIA-knowledge-graph
open index.html        # or: python -m http.server 8000
```

That's it. No build step, no dependencies to install.

---

## Build one for your own book

The graph was generated from the DDIA PDF with a small Python script. The approach is reusable for any book with a clean table of contents:

1. Extract the TOC with `pymupdf` — every heading becomes a node.
2. Hand-author a concept library: `(name, description, chapter_id, aliases, related_names)`. ~15–20 concepts per chapter, 2–4 sentence descriptions in your own words. This is the labor-intensive step, and also the valuable one.
3. Build edges: containment (book → part → chapter → …), primary (concept → home chapter), related (concept ↔ concept), and mentioned-in (concept → other chapters via alias matching).
4. Serialize to JSON and inline into the HTML template (see the `<script>` block in `index.html`).

Open an issue if you'd like me to extract this into a proper CLI.

---

## Roadmap

- [ ] Expand from 198 to ~400 concepts with worked examples
- [ ] Export as Obsidian vault (folder of linked `.md` files)
- [ ] Export as Neo4j CSV + Cypher import script
- [ ] Quiz/flashcard mode per chapter
- [ ] Port the pipeline to other books

---

## Credits

Concepts and chapter outline from Martin Kleppmann's *[Designing Data-Intensive Applications](https://dataintensive.net/)* (O'Reilly, 2017). This graph is a study aid and does not include the book's text — if you haven't, buy the book.

Graph rendering: [D3.js](https://d3js.org/) v7. Built by Sai Sugun.

## License

MIT — see [LICENSE](LICENSE).
