# Product Requirement Document

# [Aurora Flight Portfolio] — Vibe-Coding PRD (UXD Master)

**Project Vibe:** An immersive, glassmorphic digital portfolio that transforms a static academic profile into an ethereal, interactive journey using eVTOL themes and fluid aesthetics.

Date: 2025-10-25 (Current Semester) | Author(s): [Your Name] | Version: v1.0

Links: [GitHub Repo] · [Antigravity Chat] · [CV.md]

---

## 1) Core Context — “Master Prompt”

- **Problem:** Standard academic websites are often static, text-heavy, and lack personality, failing to engage visitors or showcase the dynamic nature of UX and engineering work1111.
- **Solution:** A customized "Aurora Glass" themed portfolio that utilizes interactive storytelling (gamified paper exploration) and multi-modal content (audio/visual CV) to showcase professional identity.
- **Target Users:** Academic Peers, Recruiters, UX Designers, Professors.
- **Primary Use Cases:**
    1. A recruiter exploring the candidate's work history via an interactive timeline.
    2. A peer reading the "eVTOL" paper through an immersive drone-flight visualization.
    3. A visitor listening to the audio summary (podcast) of the CV.
- **North-Star Success Metric:** Completion of all 4 Hackathon Milestones (Theme, Hero, CV, Project) with functioning interactive elements deployed on GitHub Pages.
- **Non-Goals:** Building a full backend database (will rely on static Jekyll structure); creating a new blog post engine (using existing).

---

## 2) UX Foundations (Vibe, Research, Accessibility)

- **Personas:** "The Skimmer" (Recruiter looking for quick info), "The Explorer" (Peer interested in the eVTOL research).
- **Emotional & Contextual “Vibe” Principles (The "Aurora Glass" Theme):**
    - **Aesthetic:** Ethereal, Modern, High-tech but soft.
    - **Palette:**
        - *Background:* Mesh Gradient (animated/fluid) blending **Lilac (#C4B5FD)**, **Soft Peach (#FDBA74)**, and **Mint (#6EE7B7)**.
        - *Glass:* Semi-transparent white (`rgba(255, 255, 255, 0.2)`) with `backdrop-filter: blur`.
        - *Text:* **Deep Charcoal** or **Dark Violet** for contrast.
    - **Typography:** **Inter**, **Satoshi**, or **Outfit** (Modern Sans-Serif).
- **Accessibility & Inclusion Requirements:**
    - Tri-modal CV consumption (Text, Visual, Audio)222222222.
    - High contrast text compliance despite the glass background.
    - Keyboard navigation for the interactive "Drone" map.
- **High-Level Journey:** Landing (Hero) -> Interactive Timeline (CV) -> Immersive Project View (Drone Map).

---

## 3) Scope & Priorities

- **MVP (V1) Goals:**
    1. **Milestone 4:** Implement "Aurora Glass" CSS Theme3.
    2. **Milestone 5:** Personalized Hero Section with quick links4.
    3. **Milestone 6:** Interactive Timeline & Audio CV5.
    4. **Milestone 7:** Gamified "eVTOL" Paper Explorer6.
- **Out of Scope for V1:** Detailed blog migration, dark mode toggle (focusing on Aurora Light/Glass theme first), mobile-native app.
- **Assumptions & Risks:** Antigravity can generate complex JS for the drone pathing; Github Pages builds correctly with custom JS/CSS.

---

## 4) Tech Stack & Architecture

- **Frontend:** HTML5, SCSS/CSS3 (Glassmorphism), Vanilla JavaScript (for interactions), Liquid (Jekyll Templating).
- 
    
    **Backend:** GitHub Pages (Jekyll Static Site Generator)7.
    
- **Database:** `_data` folder (YAML/Markdown) for CV and Paper content.
- **Key Libraries:** FontAwesome (Icons), potentially a lightweight animation library (GSAP) if Antigravity suggests it for the Drone, otherwise native CSS/JS.
- 
    
    **Deployment:** GitHub Pages via Git actions8.
    

---

## 5) Feature Modules (Prompt-by-Prompt, Build the MVP)

### **Module 1: The "Aurora Glass" Theme (Milestone 4)**

- **Priority:** P0
- **User Story:** "As a visitor, I want to feel a modern, ethereal vibe so that I understand the designer's aesthetic immediately."
- **Acceptance Criteria:**
    - [ ]  Background is a fluid mesh gradient of Lilac, Soft Peach, and Mint.
    - [ ]  Navigation and Content Cards use `backdrop-filter: blur(10px)` and white transparency.
    - [ ]  Font families updated to Inter/Satoshi.
    - [ ]  Text colors are dark charcoal/violet for readability.
    - [ ]  **Git Tag:** `Theme done`9.

### **Module 2: Hero Landing Page (Milestone 5)**

- **Priority:** P0
- **User Story:** "As a recruiter, I want to see a photo, tagline, and quick links immediately."
- **Acceptance Criteria:**
    - [ ]  Profile picture (`profile.jpeg`) displayed with a soft glow border.
    - [ ]  Tagline (extracted from `CV.md`) displayed prominently.
    - [ ]  Quick access buttons (Glass style) to "Interactive CV" and "eVTOL Project".
    - [ ]  **Git Tag:** `Hero done`10.

### **Module 3: Interactive & Audio CV (Milestone 6)**

- **Priority:** P1
- **User Story:** "As a user, I want to explore career history interactively and listen to a summary while browsing."
- **Acceptance Criteria:**
    - [ ]  **Visual:** Horizontal or Vertical interactive timeline.
    - [ ]  **Interaction:** Hovering over timeline nodes (Work/Education) opens a glass popup with details (from `CV.md`).
    - [ ]  **Audio:** An HTML5 Audio Player embedded for the Podcast/Summary.
    - [ ]  **Text:** A link to the standard accessible text version.
    - [ ]  **Git Tag:** `CV done`11.

### **Module 4: eVTOL Drone Map (Milestone 7)**

- **Priority:** P1 (The "Wow" Factor)
- **User Story:** "As a peer, I want to 'fly' through the research paper to understand the methodology."
- **Acceptance Criteria:**
    - [ ]  **Background:** Top-down landscape (SVG or Canvas).
    - [ ]  **Avatar:** A small Drone/eVTOL icon.
    - [ ]  **Mechanism:** "Fly" (Scroll or Click) along a wavy path.
    - [ ]  **Waypoints:** Trigger popups for Abstract, Method, Results.
    - [ ]  **Interactivity:** Images/Charts expand on hover.
    - [ ]  **Download:** PDF download link at the final destination.
    - [ ]  **Git Tag:** `Paper done` / `Project done`12.

---

## 6) AI Design & Prompting Strategy (for Antigravity)

- **System Prompt:** "You are an expert Frontend Developer and UX Designer specializing in 'Glassmorphism' and 'Creative Coding'. You are modifying a Jekyll-based academic site. Focus on CSS3 functionality, Mesh Gradients, and Vanilla JS for interactions."
- **Prompt Bank (Examples):**
    - *Theme:* "Create a CSS class `.aurora-bg` that uses a keyframe animation to blend #C4B5FD, #FDBA74, and #6EE7B7 in a mesh gradient."
    - *Drone:* "Write a JavaScript function that moves an SVG element (id='drone') along a wavy SVG path based on the user's scroll percentage."
- **Reasoning Boosters:** Use "Chain of Thought" when asking Antigravity to build the Drone logic (e.g., "First define the HTML structure, then the CSS positioning, then the JS scroll listener").

---

## 7) IA, Flows & UI

- **Information Architecture:**
    - Home (Hero + Intro)
    - CV (Timeline + Audio)
    - Portfolio/Research (The eVTOL Map)
    - Blog (Standard list)
- **Key Flows:**
    - *Paper Flow:* Start -> Scroll/Fly -> Abstract Popup -> Method Popup -> Results Popup -> Download.
- **Design Tokens:**
    - `-glass-bg`: `rgba(255, 255, 255, 0.2)`
    - `-blur-amt`: `12px`
    - `-primary-text`: `#2D2438` (Dark Violet)

---

## 8) Iteration Plan & Workflow

- **Build Rhythm:**
    1. **Setup:** Confirm `CV.md` and `profile.jpeg` are in the repo.
    2. **Sprint 1:** Apply Global CSS Variables (Colors/Fonts) & Hero.
    3. **Sprint 2:** Build the CV Timeline Component.
    4. **Sprint 3:** Build the Drone Map logic.
- 
    
    **Versioning:** Commit often with the specific milestone tags required by the Hackathon Guide13.
    

---

## 9) Quality: Testing, A11y, Performance

- **Testing:** Verify the site loads on GitHub Pages (check for Jekyll build errors).
- **Accessibility:** Run a Lighthouse check. Ensure the "Glass" effect doesn't make text unreadable (add text-shadows or increase opacity if needed).
- **Performance:** Optimize the "Top Down Landscape" image for the Drone map so it doesn't lag on scroll.

---

## 10) Metrics & Analytics

- **Events:** Track clicks on "Download PDF" and "Play Audio".
- **Dashboards:** Use the **Hackathon Dashboard** to verify Milestones are checked off14.

---

## 11) Launch & Ops

- **Environments:** `localhost:4000` (Local Jekyll) -> `username.github.io/repo` (Production).
- **Rollout Plan:**
    1. Push Theme changes -> Verify.
    2. Push Hero -> Verify.
    3. Push CV -> Verify.
    4. Push Paper -> Verify.
    5. 
        
        **Final Step:** Submit Pitch15.