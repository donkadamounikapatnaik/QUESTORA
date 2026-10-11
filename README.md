# QUESTORA — The Complete Adaptive, Game-Based Learning Platform
> **Tagline: Play. Discover. Master.**

QUESTORA is a fully functional, browser-based mathematics adventure and adaptive learning platform for students in **Class 1 to Class 10**. It transforms mathematics education into an interactive quest where students explore curricula, solve challenges, receive real-time personalized instruction, and improve through gameplay.

---

## 🌟 Complete Connected Student Journey

QUESTORA follows an end-to-end connected learning workflow with persistent state and multi-profile isolation:

```
Student Login ──► Personalized Welcome ──► Class & Topic Onboarding ──► Optional Pre-Assessment
                                                                                  │
                                                                                  ▼
Student Dashboard ◄── Post-Assessment ◄── In-Game Learning ◄── The Lost Crystal Kingdom Game
      │                                                                           ▲
      ▼                                                                           │
Performance Analytics SVG (Scores Over Time, Topic Accuracy, Pre vs Post Gain) ───┘
```

1. **Student Login Page**:
   - Collects Student Name (minimum 2 letters), Age (5 to 18 years), and Email Address.
   - Real-time inline field validation prevents malformed data or duplicate submissions.
   - Multi-profile isolation (`questora_student_v1_registry`): each student profile maintains distinct progress, XP, completed levels, and assessment records.
   - Explicit disclaimer that this is local client-side profile storage (no passwords stored in `localStorage`).

2. **Personalized Welcome Page**:
   - Greets student dynamically: *"Hi, [Student Name]! Welcome to QUESTORA!"*.
   - Displays student details badge (Age, Email).
   - Dynamic **"Continue Adventure"** button appears when saved progress exists.
   - Functional actions: Start Learning, View My Dashboard, Change Preferences.

3. **Student Onboarding**:
   - Class selection: Class 1 to Class 10 with age-appropriate visual themes.
   - School boards & curricula: **CBSE**, **NCERT-Aligned Learning** (with clear note explaining NCERT is a textbook/curriculum framework, not an examining board), **Andhra Pradesh State Board (SCERT)**, **Telangana State Board (SCERT)**, **ICSE**, and **Universal State Board**.
   - Preferred learning language toggle: English & Telugu (తెలుగు) with dynamic live updates.
   - Starting Game Difficulty: Level 1 Beginner (Crystal Meadow), Level 2 Intermediate (Enchanted Forest), Level 3 Advanced (Crystal Citadel).
   - Scored practice question counts: 5 (Quick), 10 (Standard), 15 (Extended), or Custom (3–25).

4. **Optional Pre-Assessment**:
   - Diagnostic baseline check tailored to the selected grade and topic.
   - Saves student answers, score, and topic-wise performance into persistent assessment history without hints during testing.
   - Skips cleanly if preferred, noting that no baseline score is available.

5. **Personalized Learning Path**:
   - Displays diagnostic status (baseline score or skipped state) and recommended focus areas.
   - Visual 3-stage roadmap: Meadow Fundamentals ➔ Forest Reasoning ➔ Citadel Mastery.

6. **The Lost Crystal Kingdom (Browser Adventure Game)**:
   - Full 2D Canvas RPG with keyboard (WASD/Arrows), tap-to-move, and mobile virtual D-Pad.
   - Controllable explorer character navigating dynamic maps.
   - 3 Progressive levels:
     * **Level 1 (Crystal Meadow)**: Beginner exploration, introductory gates, quantity shard attunement.
     * **Level 2 (The Enchanted Forest)**: Intermediate pathing, multi-step gates, fraction resonator.
     * **Level 3 (The Crystal Citadel)**: Advanced citadel, rune balancing, citadel guardian.
   - 4 Working mathematical game mechanics:
     * **Mechanic A (Crystal Gate)**: Mathematical barrier requiring correct answer, with hint ladder, retry, and in-game learning.
     * **Mechanic B (Collectible Crystal Puzzle)**: Hands-on manipulative task before crystal shard is attuned.
     * **Mechanic C (Interactive Number Bridge)**: Interactive number line traversal with directional stepping buttons (+1, +2, +3, -1) and live reasoning trail.
     * **Mechanic D (Citadel Guardian)**: Multi-stage shield layer dismantling leading to the royal victory scene.

7. **In-Game Learning ("Learn This Concept")**:
   - Encounter a challenge ➔ choose **Try Again**, **Get a Hint**, or **Learn This Concept** (accessible before answering or after mistakes).
   - Pauses game and strictly preserves player coordinates, inventory, level, and active puzzle state.
   - Class-adaptive interactive visual models:
     * **Classes 1–4**: Mango Orchard (Concrete Objects ➔ Pictures ➔ Number Sentences)
     * **Classes 5–6**: Fraction Bars & Slices (Equal Parts & Wholes)
     * **Classes 7–8**: Dynamic Algebra Balance Scale ($x + 7 = 15$)
     * **Classes 9–10**: Cartesian Coordinate Plane & Distance Formula ($d = \sqrt{(\Delta x)^2 + (\Delta y)^2}$)
   - Guided practice interactive check before returning to solve the original gate without premature credit.

8. **Post-Assessment & Growth Measurement**:
   - Comprehensive verification covering taught learning objectives.
   - Records chronological results into student history and computes comparative growth delta.

9. **Student Dashboard & Recommendations**:
   - Displays student name, age, email, active class, and curriculum board.
   - Displays XP, Stars, Kingdom Crystals (Discovery, Harmony, Mastery), and cleared levels.
   - Pre-assessment vs. Post-assessment comparative gain card (+Δ%).
   - Chronological assessment history table.
   - Mastered learning objectives list.
   - Personalized weak-topic recommendations ("Let's Improve These Topics!") with working revision lessons and targeted 5-question retests that dynamically update mastery status.

10. **Interactive SVG Performance Analytics**:
    - Clearly visible **"📈 Performance Graph"** button on the Student Dashboard.
    - Zero fabricated data: generated strictly from verified student attempts.
    - Three interactive SVG visualizations:
      * **1. Assessment Scores Over Time**: Chronological trend line of all Pre-tests, Post-tests, and Retests.
      * **2. Topic-Wise Accuracy**: Color-coded accuracy bars (Green $\ge 80\%$, Amber $50-79\%$, Red $< 50\%$) with correct/attempt counts.
      * **3. Pre-Assessment vs Post-Assessment Comparison**: Dual comparative bar chart with gain delta.
    - Honest empty states displayed when no assessment history exists yet.

---

## 🚀 How to Run

QUESTORA is a zero-dependency, self-contained client-side web application.

### Option 1: Direct in Browser
Open `index.html` directly in any modern web browser (Edge, Chrome, Firefox, Safari).

### Option 2: Local HTTP Server (Python)
In PowerShell or Command Prompt:
```powershell
cd C:\Users\HP\.gemini\antigravity\scratch\questora
python -m http.server 8000
```
Then visit `http://localhost:8000` in your browser.

---

## 🧪 Acceptance Test Suite (Tests A to J)

Run the test suite by opening `tests/test_runner.html` or clicking **"🧪 Run System Tests"** directly on the QUESTORA homepage:

- **Test A: Existing Functionality & Playable Game Core** — Validates character controller, 2D canvas rendering, HUD updates, crystal collection, and game loops.
- **Test B: Student Profile & Onboarding Preferences** — Validates login form validation, multi-grade curriculum loading (Classes 1–10), board selection (CBSE, NCERT-aligned, SCERT), and starting difficulty.
- **Test C: Pre-Assessment & Personalized Learning Path** — Validates diagnostic baseline question generation, score tracking, skip path, and roadmaps.
- **Test D: Four Working Mathematical Game Mechanics** — Validates Crystal Gate, Collectible Crystal Puzzle, Number Bridge traversal, and Citadel Guardian.
- **Test E: Learn This Concept Inside the Game** — Validates game state suspension, preservation of coordinates/inventory, and resume mechanics.
- **Test F: Class-Adaptive Learning Models (Classes 1–10)** — Validates Concrete Mango Orchard, Fraction Bars, Balance Scale, and Cartesian Plane models.
- **Test G: Post-Assessment & Comparative Growth** — Validates post-test evaluation, growth calculation, and mastery verification.
- **Test H: Student Dashboard & Performance Analytics SVG** — Validates score timelines, topic accuracy bars, and comparison graphs without fabricated fallback data.
- **Test I: Evidence-Based Recommendations & Retest Mastery** — Validates weak-topic detection, remediation workflows, and targeted retesting.
- **Test J: Reliability, Multi-Profile Isolation & Persistence** — Validates multi-profile data isolation (`Student Alpha` vs. `Student Beta`), session resumption, and duplicate submission guards.
