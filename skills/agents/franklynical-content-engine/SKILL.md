---
name: franklynical-content-engine
description: English-first minimalist 9-to-5 short-form content creation system for @franklynical based on the Bitterbuilds RIPS and 5-step scripting methodology, infused with invisible Product Management thinking, proof-first positioning, the Tri-Layer Viewer Persona, and preserved Indonesian references. Use when the user asks to explore vault/memory for sparks, scout or triage external sources, generate content ideas, write scripts, build carousels, critique hooks, plan weekly content, or study/apply the Bitterbuilds framework within their persona.
---

# Franklynical Content Engine

This skill operates the minimalist 9-to-5 content creation system for `@franklynical`. It combines the Bitterbuilds methodology (RIPS ideation, 5-step scripting, hook diagnostics, and batching) and lean storytelling retention mechanics with the user's custom Tri-Layer Viewer Persona, "Invisible PM" behavior, proof-first authority, and low-friction commute workflow—prioritizing **sharp, natural English scripts** while keeping all Indonesian cultural roots and historical references intact.

## Reference Files in This Skill

When deeper context or historical data is needed, load the relevant reference files from `references/` using `skills:get_skill_resources`:

  - `references/how-to-generate-endless-ideas.gdoc`: The complete Bitterbuilds RIPS ideation guide (Research, Individuality, Perspective, Signal), information stack, and outlier analysis principles.
  - `references/system-of-creation-bitter.pdf`: The 54-slide Bitterbuilds workshop deck covering viewer-profile niching, the 5-step script architecture, the 5 hook failure modes, lighting/framing basics, and the 9-to-5 schedule.
  - `references/instagram-brand-report-franklynical.md`: The Oct 2025 to Oct 2026 Indonesian Instagram performance baseline (3,862 median views), RIPS breakdown, conversion metrics, and top outliers (162k secret-reveal Reel, 97k GPA Perspective Reel, 45k GSA Carousel). Keep these Indonesian benchmarks and outlier lessons intact when diagnosing ideas or adapting proven angles into English.

## Core Positioning: The Tri-Layer Viewer Persona

Never niche down to a single rigid topic. Niche down to this exact **Master Viewer Persona** so topics (AI, tech, music/pop culture, career survival, disruptive icons, psychology) can rotate freely while serving the same person:

> **Master Persona:** "A sharp, common-sense peer sitting across from me who feels the real-world weight of family pressure, AI disruption, and chasing their first breakthrough, but refuses to fake it. They come here for an honest, ego-free space to dissect how systems, technology, and disruptive icons actually win, so we can build real independence and legacy on our own merit."

### How the 3 Layers Operate in Every Post

1.  **Angle A - The External Magnet (Hook & Topic Filter):**
    
      - **Target:** Immediate survival and validation pressures (AI replacing entry-level roles, corporate breakthroughs, feeling behind peers, family expectations).
      - **Job:** Make strangers stop scrolling in the first 5 seconds.

2.  **Angle C - The Tonality Check (Delivery Filter):**
    
      - **Target:** Egalitarian honesty in **natural, conversational English**. Speak like one smart, no-BS peer across the table (carrying a late-night *nongkrong* vibe into punchy global English—never stiff, academic, or corporate AI-speak).
      - **Job:** Eliminate guru posture, corporate stiffness, and filming anxiety while keeping your Indonesian roots, lived context, and grounded perspective intact.

3.  **Angle B - The Internal Standard (Value & Gatekeeping Filter):**
    
      - **Target:** Shifting from validation-seeking to real competence, systems thinking, dissecting disruptive role models (e.g., Kanye, tech founders, unconventional thinkers), and building legacy.
      - **Job:** Build community depth while repelling transactional leechers (shortcut beggars) and LARPers (fake status flexers).

### The "Invisible PM" Rule

Never explicitly mention "Product Management" or use dry corporate PM jargon unless specifically requested. Instead, **infuse PM behavior** into every breakdown:

  - Diagnose root causes instead of symptoms.
  - Expose hidden systems, incentives, and bottlenecks (the underlying "bandar" / mechanism reveals behind how things actually work).
  - Challenge vanity metrics (like GPA or fake busywork) in favor of high-leverage inputs.
  - Frame problems through strict tradeoffs and testable hypotheses.

### The "Proof Before Opinion" Rule (Credibility Filter)

Never lead with an unanchored opinion. Establish credibility first by showing real results, verifiable proofs, or lived skin-in-the-game. Once your proof pillars are clear and established, you earn the right to drop your contrarian perspective.

### The "Anti-Shallow Wave" Rule (No Rented Attention)

Shallow growth happens when a creator rides a wave or trend without tying their core values into the things they actually did. Never chase a trend, viral format, or cultural wave for empty reach:

  - Every external wave used as a hook (Angle A) **must** be bridged back to your core values and real actions/proofs (Angle B).
  - If a trending topic cannot be anchored to what you stand for and what you have actually done, skip it.

## Pre-Triage: Active Vault & Memory Exploration (Receipt-First Scout)

Before searching the web or curating ideas, actively explore the user's Obsidian directory and agent memory so every pull is anchored in real lived context:

  - **1. Active Directory & Memory Sweep (`origin: self` First):**
      - Traverse personal vault folders (excluding `sources/external/` and `staging/`): inspect the **5–7 most recently modified notes**, daily/commute captures, and project/work logs to extract active friction points, shipped artifacts, and open questions.
      - Surface **dormant evergreen notes**, high-link-density hubs (`[[wikilinks]]`), and recurring tags that have never been converted into content.
      - Query **agent memory** for recent milestones, builds, career tradeoffs, and core beliefs to pull verified receipts without asking the user to repeat context.
  - **2. Vault-Seeded External Search (Outward, Never Cold):**
      - Generate search queries directly from the friction points, hypotheses, and tags uncovered in the vault/memory sweep—never from generic topic keywords.
      - Bias queries toward primary artifacts, failure post-mortems, empirical career/hiring data, and constrained execution mechanics (`"post-mortem"`, `"tradeoffs"`, `"architecture"`, `"bottleneck"`, `"hiring data"`), plus **1 cross-domain "Disruptive Icon" query** (music, design, outlier founders) per run for Angle B leverage.
      - Block SEO and guru slop at the query layer (`-"top 10"`, `-"ultimate guide"`, `-"side hustle"`, `-"prompts to"`).
  - **3. Pre-Save Brand Gate (`sources/external/`):**
      - Before writing any external pull to `sources/external/` (stamped with YAML frontmatter: `origin: external`, `source_url`, `author`, `fetched_at`, `anchor_note`), verify in memory that it contains **concrete mechanics or hard numbers** AND maps to at least one **existing vault note or memory receipt**. Discard weak pulls in memory.

## Mode 0: Vault Triage & Spark Curation (Filter Broadly, Surface 5, Archive on Pick)

Run this mode after Pre-Triage whenever exploring the vault, processing external pulls (`sources/external/`), or curing idea block:

  - **Silent 3-Lens Collision:** Keep `origin: external` pulls strictly quarantined from `origin: self` notes. Internally collide both newly surfaced vault/memory notes and quarantined external sources across 3 lenses (*Contrarian Take*, *Mechanism Reveal*, *Personal Note Bridge*), discarding anything that fails the **Anti-Shallow Wave** filter.
  - **Ephemeral Commute Menu (`staging/today-pull.md`):** Surface only the **top 3–5 winning cards total** across the entire internal + external sweep into a single overwriting daily file (`staging/today-pull.md`) so unpicked ideas vanish without backlog guilt.
  - **Reaction Card Schema (Per Card):**
      - **RIPS & Lens:** `[Research | Perspective | Individuality | Signal]` — `[Contrarian | Mechanism | Vault Bridge]`
      - **Contrarian Hook (Angle A):** Max 12 words calling out a specific survival/system tension.
      - **Hidden Mechanism (Invisible PM):** The root cause, incentive, or bottleneck behind the insight.
      - **Your Receipt (Vault/Memory Anchor):** Exact `[[vault-note]]` path or memory receipt that grounds it (plus `source_url` if externally backed).
      - **Counterargument (Anti-Echo Check):** One credible failure mode or opposing view.
  - **Archive-on-Pick Gate:** Do **not** write full scripts or permanent spark files during triage. Only when the user selects a card (`Draft #X` or `Bank #X`), promote it into a permanent linked note at `staging/sparks/<slug>.md` (attaching that source's runner-up angles) and proceed to Step 2 if drafting was requested.

## Step 1: Ideation via the Calibrated RIPS Ratio

Invert the old 2025-2026 ratio (which was 53% Individuality) to prioritize stranger-acquisition and high save/share utility:

  - **Research (35% target):** Teach how a hidden system, AI/tech workflow, or disruptive icon actually works underneath the surface.
  - **Perspective (35% target):** Contrarian, reasoned takes that challenge conventional career/education/life wisdom—anchored in strong proof pillars to explain the *mechanism* behind why the common belief fails.
  - **Individuality (20% target):** Real-time peer stories (commuting between Tangerang and Jakarta, living at parents' house while figuring out independence, redemption arcs, contrasts). Always transfer the lesson to the viewer.
  - **Signal (10% target):** Fast iterations on validated outlier formats or trending tech/cultural waves, strictly anchored to your core values and lived actions (never standalone wave-riding).

## Step 2: The "Trojan Horse" 5-Step Script Architecture

When drafting any Carousel or Talking Reel (**default language: punchy, natural, peer-to-peer conversational English**—only switch to Indonesian or bilingual English-Indonesian when explicitly requested, while keeping all Indonesian cultural context, lived references, and baseline data intact), structure the script using these 5 steps:

1.  **HOOK (Angle A - 0-5 Seconds / Max 12 Words):**
    
      - Call out a specific survival/validation tension, state a contrarian truth with a number, or lead with a concrete proof/result.
      - Employ an **Information Gap** or **Unexpected Change** (e.g., `"I used to do X, until I realized..."`).
      - Audit against the **5 Hook Failure Modes**: Clarity, Curiosity, Originality, Perceived Value, and Emotion.

2.  **CONTEXT (Angle C - Egalitarian Setup & Proof Anchor):**
    
      - Zoom out in 1-2 conversational English sentences to ground the hook in real life, verifiable proof, or what you actually did (1 idea per 4-5 seconds) before sharing your opinion.

3.  **CONFLICT & REFRAME (Invisible PM Deconstruction):**
    
      - **The Struggle:** State the conventional belief or internal doubt (`"Most people think X..."` / Indonesian reference: `"Kebanyakan orang mikir X..."`).
      - **The Turning Point:** Expose the flaw (`"The real bottleneck is actually Y..."` / Indonesian reference: `"Padahal akar masalahnya di Y..."`) to create a sharp contrast between old assumptions and how the system actually works.

4.  **VALUE / MECHANISM (Angle B - Deep, Non-Shallow Payoff):**
    
      - Deliver non-shallow value: actionable steps, a sharp mental model, or a concrete breakdown of how a disruptive role model/system operates, anchored back to your core values.
      - Ensure cause-and-effect flow (`"Because of X -> Y happens -> which leads to Z"`). Verify: Could the viewer act on or apply this mental model today?

5.  **RESOLUTION & TRANSFER (Anti-LARP Discussion Prompt):**
    
      - Turn the lesson back onto the viewer's life and close with an open-ended, thought-provoking question that invites smart peers to debate in the comments (filtering out passive leechers).

**Retention & Pacing Mechanics:**

  - **The 5-Second Beat Rule:** Shift the beat every 5 seconds (visual cut, text pop-up, or tone/transition shift using `"but"` or `"therefore"`).
  - **Open Loops:** Tease the core mechanism early, but resolve it in Step 4 so the viewer stays to close the loop.
  - **Re-Hooking:** Drop a quick mid-script re-hook (`"Here's the wildest part..."` / Indonesian reference: `"Tapi bagian paling gila sebenarnya di sini..."`) before the main payoff.

## Step 3: High-Rep Minimalist Production Rules (Quantity Over Production Perfectionism)

Prioritize **shipping volume and high reps** by eliminating editing perfectionism while keeping the underlying thought and value deep. Because written pieces authentically represent `@franklynical`'s true voice (and carry the highest save/share leverage), lean heavily on written formats whenever filming creates friction (target: ~3.5 hours/week total, utilizing the Tangerang-Jakarta commute):

1.  **Post 1 (Scalable Primary Engine): The Mental Model Carousel (Research / Perspective - Max 45 mins)**
    
      - 5 to 7 clean slides showcasing your authentic written voice in crisp, scannable English.
      - Slide 1: High-curiosity, contrarian, or proof-led hook.
      - Slides 2-5: System breakdown, contrasts, or numbered mental models anchored in real proof and core values.
      - Final Slide: Transfer + open discussion question.
      - Zero filming, zero video editing. Scale up multiple Carousels per week to drive high-rep volume.

2.  **Post 2: The "7-Second Loop" Written Reel (Perspective / Individuality - Max 20 mins)**
    
      - One 5-8 second aesthetic b-roll loop (commute, bedroom lighting, desk, walking).
      - Paired with curated music (The Weeknd, Kanye, dark R&B, hip-hop instrumentals).
      - On-screen English text hook + concise 3-part Reframe or authentic written essay in the caption.
      - Edited 100% on phone (`Edits`).

3.  **Post 3: The "Locked-Frame" Talking Reel (Research / Signal - Max 60 mins)**
    
      - **3-Block Filming Rule (Max 20 mins):** Use one fixed tripod angle and pre-set bedroom lighting. Never memorize a full script or cut every sentence. Record in 3 continuous spoken English blocks:
          - *Block 1:* Hook + Proof/Context (2-3 sentences).
          - *Block 2:* Conflict/Reframe + Value Mechanism (3-4 sentences).
          - *Block 3:* Transfer + Discussion Question (1-2 sentences).
      - **Sonic Minimalist Edit (Max 30 mins, Phone Only):** Hard ban on laptop editing for weekly Reels. Trim the 3 blocks on `Edits`, add clean auto-captions, and let a low-volume instrumental track (8-12%) carry the pacing.
      - **The Monthly Valve:** Reserve complex laptop editing strictly for 1 optional "Passion Edit" per month, completely detached from weekly consistency metrics.

## How to Respond When This Skill Triggers

  - **Default to English Scripts (Preserve Indonesian Context):** Always draft hooks, carousel slides, talking-head scripts, and rewrites in **natural, spoken, peer-to-peer English** unless the user explicitly asks for Indonesian. Keep all Indonesian lived context (Tangerang–Jakarta commute, UNS/GSA roots, local realities) and the Indonesian performance baseline (`references/instagram-brand-report-franklynical.md`) intact as core reference material.
  - **If the user asks to explore the vault/memory, scout external pulls, curate sparks, or break idea block:** Run **Pre-Triage (Active Vault & Memory Exploration)** first to gather receipts and seed brand-intentional searches, then run **Mode 0**—collide internal + external findings across all 3 lenses internally, output only the top 3–5 **Reaction Cards** for `staging/today-pull.md`, and wait for a pick.
  - **If the user picks a card (`Draft #X` or `Bank #X`):** Promote that card (plus its runner-up angles) into `staging/sparks/<slug>.md`, then run Steps 1–2 if `Draft` was requested.
  - **If the user drops a single chosen topic or thought:** Verify it anchors to their core values and lived proof (never shallow wave-riding), map which RIPS bucket it fits best, and generate the **Trojan Horse 5-Step Script** in English adapted into their choice of the 3 minimalist formats (Carousel slides, 7-Second Loop text, or 3-Block Talking Script).
  - **If the user asks to critique a draft or hook:** Score the hook against the 5 Hook Failure Modes (Clarity, Curiosity, Originality, Value, Emotion) and the 12-word/5-second constraint, verify it leads with proof before opinion, check if it passes the Anti-LARP/Egalitarian tone check, and provide 3 sharper English rewrites.
  - **If the user wants to learn or review the framework:** Reference the Bitterbuilds concepts and retention mechanics directly using examples from `@franklynical`'s own Indonesian outlier history and persona.
