# Smart Reading Tracker (Vibe Coded with Claude)

> A CSV-powered reading recommendation engine built by vibe coding with Claude in one afternoon.

**What it does**
- Ingests Goodreads ratings
- Ingests Libby wishlists
- Scores and ranks what you should read next
- Warns you about potential DNFs

Built by iterating in conversation instead of writing specs.

## Try it

App: https://claude.ai/public/artifacts/4d32b214-5a9b-4492-84ce-0ffec47720df

1. Export your Goodreads ratings as CSV  
2. Export your wishlist as CSV  
3. Upload them into the app  
4. Get ranked reading recommendations  

# How I Built a Smart Reading Tracker by Vibe Coding with Claude

I had a problem: too many books on my Libby wishlist and no idea which ones to read next. So I spent an afternoon **“vibe coding” with Claude** to build a custom reading tracker that analyzes my Goodreads ratings and recommends what to tackle next.

Here’s how it went down.

---

## The Vision (Starting Super Casual)

I kicked things off with a simple idea:

> *“I want to build a tool to track my reading.”*

No detailed specs. No wireframes. Just vibes.

What I had:
- A Goodreads account with my ratings from last year  
- A Libby wishlist of books I want to read  
- A vague sense that these two things should somehow connect  

Claude immediately got it and asked the right questions:
- Can you export your data?
- Do you want this to update dynamically?
- What matters most in recommendations?

---

## Building in Layers (The Fun Part)

Instead of planning everything up front, we just… built and iterated.

### Layer 1: Basic File Uploads

We started with a simple web app that could upload CSV files from:
- Goodreads
- Libby

Claude created a clean interface with three upload sections, and we tested it immediately.

---

### Layer 2: The “Oh Wait, I Need This Too” Moments

As we were building, new needs kept popping up:

- I wanted to track **DNF (Did Not Finish)** books  
  → Claude added a third upload section in seconds.

- I wanted **multiple Libby lists** (business, non-fiction, read-next, etc.)  
  → Claude updated the uploader to handle multiple files and track them separately.

This is where vibe coding shines: you don’t fight your own evolving requirements—you embrace them.

---

### Layer 3: Debug-Driven Development

Things got real when I tried uploading my **read-next** CSV… and nothing happened. No error. Just silence.

We went into full detective mode:

- Tried JavaScript `alert()` — blocked by the artifact environment  
- Switched to visual notifications  
- Found malformed CSV rows crashing the parser  
- Added better validation and error handling  

Claude didn’t just fix the bugs—it explained:
- Why browser sandboxing blocked alerts  
- How CSV parsing failed  
- Why type checking prevented crashes  

I learned more debugging in 20 minutes than in weeks of tutorials.

---

## The Algorithm (AKA The Secret Sauce)

Once the data flowed, Claude built a recommendation system that:

- **Boosts** books by authors I rated ⭐⭐⭐⭐+ on Goodreads  
- **Penalizes** books by authors I previously DNF’d  
- Adds warnings like *“Similar to a book you didn’t finish”*  
- Promotes new discoveries outside my normal patterns  

### Scoring Example

| Signal | Effect |
|------|--------|
| Favorite author | +30 |
| DNF’d author | –15 |
| Similar to DNF | Warning badge |
| Outside taste | Exploration boost |

Books with multiple red flags sink to the bottom with clear warnings.

---

## What “Vibe Coding” Actually Means

Traditional coding: Plan → Spec → Build → Test → Deploy


Vibe coding with Claude:

- Start with a fuzzy idea
- Build something
- Try it
- “Actually, can we also…”
- Iterate
- Debug in conversation
- End up with something better than planned


The final app had features I didn’t even know I wanted:
- Deleting individual lists  
- Match scores per book  
- DNF warnings before borrowing  

---

## The Technical Bits (For the Nerds)

The final app is a **React component** that:

- Uses **PapaParse** for messy CSV files  
- Stores data with **Claude’s storage API**  
- Supports **multiple uploads with deduplication**  
- Uses **real-time UI notifications**  
- Validates data types to prevent crashes  
- Scores and filters books across multiple signals  

All built in one afternoon.

---

## What I Learned

Vibe coding isn’t lazy—it’s iterative product discovery.

Claude acts as:
- A developer  
- A debugger  
- A product manager  

When something broke, we didn’t panic. We added logging, better UI feedback, and error handling. The app is stronger because of it.

The killer feature isn’t speed.  
It’s **conversation while building**.

When I saw `book.title.toLowerCase is not a function`, Claude didn’t just tell me what was wrong—it explained what it meant in plain English and how to fix it.

---

## What’s Next

Now I have a reading tracker that actually helps me decide what to read.

My Libby wishlist went from **100+ overwhelming books** to a **ranked, scored list with explanations**.

Could I have built this alone? Sure—eventually.  
But vibe coding with Claude got me there **in one afternoon**… with time left to write this post.

And honestly? That’s the future of coding I’m excited about.

---

## Stats

- **Tools used:** Claude (Sonnet 4), React, PapaParse, Tailwind CSS, caffeine  
- **Time to build:** One afternoon  
- **Times I said “actually, can we also…”:** At least 15  
- **Books I’m now avoiding because they resemble DNFs:** 7 😅  




