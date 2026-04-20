# LinkedIn post — draft

Below are a few length options. Pick whichever fits. LinkedIn rewards posts that get read, so the shorter versions usually travel further — but the longer one is there if you want to show the work.

---

## Option A — Short (best for feed engagement, ~150 words)

I tried to read *Designing Data-Intensive Applications* three times. Bounced off every time.

It's not that the book is bad — it's that every chapter references four other chapters, and linear reading just can't hold that web of ideas in your head.

So last week I stopped reading it and started mapping it.

I turned the whole book into an interactive knowledge graph — 198 concepts across 12 chapters, every connection visible, every node searchable.

Something clicked. When I can *see* that "Reliability" touches replication, partitioning, and consensus all at once, the cross-references stop feeling like interruptions and start feeling like the actual point.

Graph-shaped content deserves graph-shaped study tools. Linear notes are a lossy compression of how the ideas actually relate.

I put it on GitHub in case it helps anyone else who's been stuck on DDIA:
👉 https://sugun-ravipalli.github.io/DDIA-knowledge-graph/

Fork it, break it, build one for your own book.

#DistributedSystems #DDIA #LearningInPublic

---

## Option B — Medium (~250 words, the one I'd post)

I tried to read *Designing Data-Intensive Applications* three times over the last two years. I bounced off every single time.

It wasn't the book. Kleppmann's writing is excellent. The problem was me, or more accurately, the shape of how I was trying to learn it.

DDIA is a book where Chapter 5 quietly depends on something from Chapter 9, and Chapter 7 casually reuses a concept from Chapter 2. Linear reading makes you carry all of that in working memory, and mine just wouldn't stretch that far.

So this weekend I tried something different. I turned the whole book into an interactive knowledge graph.

198 hand-authored concepts. 12 chapters. 1,255 edges between ideas. Click "Reliability" and you can see — at a glance — every chapter and concept it touches. Search "consensus" and the graph lights up wherever it appears. Drag nodes around until the structure makes sense *to you*.

Something finally clicked. The cross-references that used to interrupt me now feel like the whole point.

I think this is the real lesson: some material is graph-shaped, and forcing it through a linear format (a book, a blog post, a lecture) is a lossy compression. When the ideas are a web, the study tool should be a web too.

Put it on GitHub Pages in case it helps anyone else who's stared at DDIA's spine guiltily for a few years:

👉 https://sugun-ravipalli.github.io/DDIA-knowledge-graph/

The code's open — fork it and build one for your own book.

#DistributedSystems #DDIA #LearningInPublic #SoftwareEngineering

---

## Option C — Long (~380 words, for when you want to make the argument)

I tried to read *Designing Data-Intensive Applications* three times. I bounced off every time.

Not because the book is bad. Kleppmann's writing is excellent and the book is a minor miracle of clarity on hard problems. The issue was the shape of the learning, not the content.

DDIA is a web, not a line. Chapter 5 (replication) quietly depends on concepts from Chapter 9 (consistency, consensus). Chapter 7 (transactions) reuses ideas from Chapter 2 (data models). Every paragraph has three silent footnotes to other paragraphs, and a linear read makes you carry all of that context in working memory.

Mine kept overflowing. So a few evenings ago I stopped reading it and started mapping it.

I turned the whole book into an interactive knowledge graph.

• 1 book → 3 parts → 12 chapters → 54 sections → 127 subsections
• 198 hand-authored concepts, each with a description
• 1,255 edges: structural containment, primary coverage, related concepts, cross-chapter mentions
• Concepts numbered like `[Ch.9·03]` so you can still read the book in order — the graph just shows you the seams

Then something clicked.

When I can SEE that "Reliability" connects to replication, partitioning, fault tolerance, and consensus all at once, the cross-references stop feeling like interruptions and start feeling like the actual point. The graph made the book's structure visible in a way reading never did.

I think this generalizes. Some material is graph-shaped — concepts that only make sense in relation to each other. Databases. Distributed systems. Compilers. Most of advanced math. Forcing graph-shaped content through a linear format (book, blog, lecture) is a lossy compression of the thing you actually want to learn.

We've had a century to get comfortable with linear study — highlighters, outlines, flashcards. We've barely started on graph-native study tools. I suspect that's where a lot of the next generation of learning software is going to live.

For now, one graph for one book:

👉 Live: https://sugun-ravipalli.github.io/DDIA-knowledge-graph/
👉 Code: https://github.com/Sugun-ravipalli/DDIA-knowledge-graph

Fork it. Break it. Build your own for whatever book has been sitting guiltily on your shelf.

If you've also bounced off DDIA, try reading it as a graph. See if it clicks for you too.

#DistributedSystems #DDIA #LearningInPublic #SoftwareEngineering #KnowledgeGraphs

---

## Posting tips

- LinkedIn truncates the preview after ~3 lines. Put the hook (the "I tried to read it three times" line) right at the top so it lands before the "see more" fold.
- Screenshots or a short screen-recording of the graph in action will roughly double engagement. Record 15-20 seconds of you searching "Reliability" and dragging a few nodes around.
- Post mid-morning on a Tuesday, Wednesday, or Thursday (LinkedIn's best windows).
- Reply to every comment in the first hour — LinkedIn's algorithm weighs early engagement heavily.
- Pin the repo link as the first comment if you want more feed reach; LinkedIn down-ranks posts with outbound links in the body.
