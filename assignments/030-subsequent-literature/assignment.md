# Assignment: Subsequent Literature Bibliography

**Due:** Before next class

**Prerequisite:** [PaperPile Bibliography](../020-paperpile-bibliography/assignment.md) — you need your `.bib` file first.

---

## Objective

Create a BibTeX file containing papers that have **cited** your ballpark paper (the "subsequent literature").

---

## Ask Cursor First

Before diving into LitMaps, open Cursor and ask:

> "I have a paper titled [your ballpark paper title]. I want to find papers that have cited it since publication. What's the best way to do this, and what should I look for when selecting which citing papers are most important?"

This helps you think about your approach before starting the mechanical steps.

---

## Background

Your ballpark paper was published at some point in the past. Since then, other researchers have cited it. These **citing papers** represent the "subsequent literature" — work that builds on, extends, or responds to your paper.

LitMaps can identify these citing papers and export them as a .bib file.

---

## Free account limitations

LitMaps free accounts have limits:
- **2 maps** total
- **100 articles per map**
- **20 search inputs**

This is sufficient for this assignment if you work strategically.

---

## Steps

### 1. Sign in to LitMaps

Go to https://www.litmaps.com and sign in (or create a free account).

---

### 2. Import your ballpark paper's bibliography

1. Click **Import** (top left)
2. Select the .bib file you exported from PaperPile
3. Click **Import**

This adds your ballpark paper's references to LitMaps.

---

### 3. Find your specific ballpark paper

Your imported .bib may contain many papers. You need to identify the **one paper** that is the subject of your ballpark entry.

1. In LitMaps, use the search bar to find your ballpark paper by title or author
2. If it doesn't appear in search, check "My Articles"

---

### 4. Create a LitMap focused on citing papers

1. Click **New Litmap**
2. Add your ballpark paper as the **seed article**
3. Click **Discover** to find related articles

---

### 5. Filter for CITING papers only

LitMaps shows both:
- Papers **cited by** your paper (backward citations — older papers)
- Papers **citing** your paper (forward citations — newer papers)

**You want only the citing papers (forward citations).**

To filter:
1. Look at the visualization — citing papers appear to the RIGHT of your seed paper
2. In the article list, look for publication dates AFTER your ballpark paper's publication date
3. Only add articles that are **more recent** than your ballpark paper

---

### 6. Add citing papers to your map

1. Click **Add to Litmap** for each paper that cites your ballpark paper
2. Prioritize:
   - Highly cited papers (indicates importance)
   - Recent papers (last 3-5 years)
   - Papers directly relevant to your ballpark topic
3. Stay within the 100-article limit — be selective

**Tip:** You don't need to add every citing paper. Focus on the most relevant 20-50.

---

### 7. Export the citing papers as BibTeX

1. With your litmap open, click the **download/export icon**
2. Select **BibTeX** format
3. Save the file as `subsequent-literature.bib`

---

### 8. Verify your export

Open `subsequent-literature.bib` in a text editor.

**Check:**
- All entries have publication dates AFTER your ballpark paper
- The file contains valid BibTeX entries (lines starting with `@article{`, `@inproceedings{`, etc.)

---

## Deliverable

A file named `subsequent-literature.bib` containing BibTeX entries for papers that cite your ballpark paper.

**Save this file** — it is required for the next assignment.

---

## Troubleshooting

**"Can't find my ballpark paper in LitMaps":**
- Try searching by DOI if you have it
- Try searching by exact title
- Some papers (especially working papers or very recent publications) may not be in LitMaps' database

**"No citing papers found":**
- Your paper may be very recent and not yet cited
- Document this — we'll discuss alternatives in class

**"Too many citing papers (>100)":**
- This is a good problem! Be selective
- Focus on the most recent and most cited
- Use your second map if needed (you have 2 maps on free accounts)

---

## Tips for success

1. **Work backward from dates:** Your ballpark paper was published in year X. Only papers from year X+1 onward can cite it.

2. **Quality over quantity:** 20 highly relevant citing papers are more valuable than 100 tangentially related ones.

3. **Check the citation relationship:** LitMaps shows connections. Make sure the arrow points FROM the newer paper TO your ballpark paper (indicating citation).
