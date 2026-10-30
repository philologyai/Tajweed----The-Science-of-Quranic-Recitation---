# Tajweed: The Science of Quranic Recitation | علم تلاوة القرآن

An immersive, beautifully crafted Android application dedicated to mastering Tajweed—the sacred art and science of Quranic recitation. Designed with an elegant Islamic heritage aesthetic featuring rich emerald greens, warm gold accents, authentic Arabic typography, interactive audio recitation clips, comprehensive rule guides, articulation point diagrams, and ear-training quizzes.

---

## User Review & Critical Decisions

> [!IMPORTANT]
> The following directions have been aligned based on your preferences:
> - **Primary Focus**: Comprehensive interactive Tajweed rules guide structured logically from foundational to advanced concepts with crystal-clear Quranic recitation examples.
> - **Audio Recitation**: Built-in recitation audio clips for each rule, letter, and example Ayah, featuring clear playback controls, speed adjustment, and audio repetition for practice.
> - **Visual Aesthetic**: Elegant Islamic heritage aesthetic featuring deep emerald green (`#0B3B24`), burnished gold accents (`#D4AF37`), warm parchment backgrounds (`#FDFBF7` / dark slate `#101F18`), and refined Islamic geometric accents.

---

## 1. Overview & Core Concept

Tajweed (تجويد) linguistically means "proficiency" or "doing something well," and in Quranic sciences refers to reciting each letter from its correct point of articulation (Makhraj) with all its inherent and conditional characteristics (Sifat).

This application transforms complex classical treatises into an intuitive, visually stunning, and phonetically rich mobile experience:
- **Interactive Rules Encyclopedia**: Full coverage of Nun Sakinah & Tanween (Izhar, Idgham, Iqlab, Ikhfa), Meem Sakinah, Qalqalah, Mudood (Elongations from 2 to 6 Harakat), Tafkheem & Tarqeeq (Heavy and Light letters), and stopping rules (Waqf & Ibtida).
- **Makharij & Sifat Studio**: Visual interactive map of articulation points (Throat, Tongue, Lips, Nasal Cavity, Empty Space) with letter grouping and phonetic characteristics.
- **Color-Coded Quranic Recitation Library**: Authentic Quranic passages with universal color-coded Tajweed markings, Arabic text in authentic Naskh calligraphy, transliteration, English explanation, and instant one-tap audio recitation.
- **Ear-Training & Interactive Quizzes**: Active listening exercises to test recognition of rules (e.g., distinguishing Idgham with Ghunnah vs without Ghunnah, detecting Qalqalah levels).
- **Personalized Bookmarking & Progress**: Track completed lessons, bookmark favorite rules, and take quick reference notes.

---

## 2. User Experience & Visual Design

### Key User Flows
1. **Explore Rules (Tab 1: Rules & Lessons)**:
   - Users browse organized categories (Nun Sakinah, Meem Sakinah, Mudood, Qalqalah, Tafkheem/Tarqeeq, Waqf).
   - Each rule screen presents: Arabic title, linguistic & technical definitions, step-by-step conditions, letter charts, and interactive Quranic examples with color-highlighted letters.
   - Tapping the audio button on any example plays the specific recitation clip demonstrating the exact rule with animated waveform indicator.
2. **Makharij & Sifat (Tab 2: Articulation)**:
   - Interactive anatomical diagram of the mouth and throat (Al-Jawf, Al-Halq, Al-Lisan, Ash-Shafatan, Al-Khayshum).
   - Selecting a zone highlights the corresponding Arabic letters, their points of contact, and attributes (Hams vs Jahr, Shiddah vs Rakhawah, Isti'la vs Istifal).
   - Audio sample for each letter with Sakinah and vowel variations (e.g., أَنْ, أَقْ, بْ).
3. **Recitation Studio & Ayah Reader (Tab 3: Practice Passages)**:
   - Curated practice Surahs and verses (e.g., Al-Fatihah, Al-Ikhlas, Al-Falaq, An-Nas, Ayatul Kursi, Al-Mulk excerpts).
   - Dynamic Tajweed legend explaining color highlights (Red = Madd, Green = Ghunnah/Ikhfa, Blue = Qalqalah, Orange = Iqlab, Gray = Silent letters).
   - Audio playback with verse repetition, playback speed (0.75x, 1.0x, 1.25x), and audio scrubbing.
4. **Quiz & Ear Training (Tab 4: Mastery Quiz)**:
   - Challenge modes: "Identify the Rule from Arabic text", "Ear Training: What rule did you hear?", and "Match the Letter to its Makhraj".
   - Instant visual feedback with celebratory emerald-gold badges and streak tracking.

### Visual Identity & Theme
```
┌────────────────────────────────────────────────────────┐
│  Primary: Deep Emerald      [#0B3B24]                  │
│  Primary Container: Forest  [#164D32]                  │
│  Accent / Gold: Radiant Gold[#D4AF37] / Warm [#E5C158] │
│  Background (Light): Parchment Ivory    [#FDFBF7]      │
│  Background (Dark): Sacred Midnight     [#0D1A14]      │
│  Surface Card: Cream Soft Paper         [#F7F4EB]      │
│  Tajweed Color Spectrum:                               │
│    - Madd (Elongation):     Ruby Crimson [#C5221F]     │
│    - Ghunnah & Ikhfa:       Jade Green   [#1E8E3E]     │
│    - Qalqalah (Echoing):    Azure Blue   [#1A73E8]     │
│    - Iqlab (Conversion):    Amber Orange [#E37400]     │
│    - Silent / Assimilated:  Soft Slate   [#80868B]     │
└────────────────────────────────────────────────────────┘
```
- **Typography**: Local Arabic font pairing with **Amiri** / **Scheherazade New** (installed locally via `font-util`) for Arabic script with full Tashkeel and Tajweed signs, paired with an elegant serif/sans display font for English explanations.
- **Islamic Heritage Accents**: Delicate 8-point geometric star motifs (Rub el Hizb ۞), arched Mihrab card headers, and gilded border trims.

---

## 3. Key Product Decisions & Trade-Offs

- **Decision 1: Audio Playback Architecture**
  - *Chosen Approach*: Multi-source audio manager with bundled essential rule clips / synthesized phonetic samples and high-quality streaming recitation feeds from verified Quranic CDNs (EveryAyah / Quran.com API audio).
  - *Why*: Delivers instantaneous offline audio for core rule pronunciations while allowing full pristine Ayah recitations without bloating the initial APK download size.
  - *Alternatives Considered*: Bundling dozens of full Surah MP3s would exceed container APK limits (200MB+).
- **Decision 2: Universal Tajweed Color Coding**
  - *Chosen Approach*: Adhere to the international standardized Medina Mushaf Tajweed color palette recognized globally by Qira'at institutes.
  - *Why*: Ensures students and learners experience zero friction or confusion compared to physical printed Tajweed Qurans.
- **Decision 3: Local Persistence for Progress & Bookmarks**
  - *Chosen Approach*: Android Room database storing lesson completion states, quiz high scores, bookmarks, and user custom practice notes.
  - *Why*: Robust, offline-first, instant retrieval without requiring external accounts or cloud latency.

---

## 4. Technical Architecture & Component Hierarchy

```
┌─────────────────────────────────────────────────────────────────────────┐
│                           MainActivity                                  │
│  ┌───────────────────────────────────────────────────────────────────┐  │
│  │                    TajweedApp (Scaffold)                          │  │
│  │  - TopAppBar with Islamic Pattern & Audio Status Indicator        │  │
│  │  - M3 NavigationBar: [Rules | Makharij | Recitation | Quiz]       │  │
│  └───────────────────────────────────────────────────────────────────┘  │
└────────────────────────────────────┬────────────────────────────────────┘
                                     │
           ┌─────────────────────────┼─────────────────────────┐
           ▼                         ▼                         ▼
┌──────────────────────┐  ┌──────────────────────┐  ┌──────────────────────┐
│     RulesScreen      │  │    MakharijScreen    │  │   RecitationScreen   │
│  - Category Filter   │  │  - Anatomical Map    │  │  - Surah Selector    │
│  - Rule Detail View  │  │  - Letter Grid       │  │  - Ayah Card Display │
│  - Arabic Examples   │  │  - Sifat Attributes  │  │  - Color Tajweed     │
│  - Audio Player Bar  │  │  - Phonetic Player   │  │  - Waveform & Loop   │
└──────────────────────┘  └──────────────────────┘  └──────────────────────┘
           │                         │                         │
           └─────────────────────────┼─────────────────────────┘
                                     │
                                     ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                           TajweedViewModel                              │
│  - State: Selected Category, Current Playing Audio, Progress, Quiz State│
│  - Repositories: TajweedRepository, AudioPlayerManager, Room DAO        │
└────────────────────────────────────┬────────────────────────────────────┘
                                     │
           ┌─────────────────────────┴─────────────────────────┐
           ▼                                                   ▼
┌──────────────────────────────────────┐  ┌───────────────────────────────┐
│           TajweedAudioPlayer         │  │         Room Database         │
│  - Android MediaPlayer               │  │  - BookmarkEntity             │
│  - Play, Pause, Seek, Loop, Speed    │  │  - LessonProgressEntity       │
│  - Audio playback state Flow         │  │  - QuizScoreEntity            │
└──────────────────────────────────────┘  └───────────────────────────────┘
```

### Core Module Breakdown
1. **`model/`**:
   - `TajweedRule.kt`: Rule categories, letters, description, conditions, Quranic examples (`AyahRef`, `ArabicText`, `AudioUrl`, `HighlightRanges`).
   - `MakhrajPoint.kt`: Articulation point definitions (throat, tongue, etc.) and letter characteristics (`Sifah`: Hams/Jahr, Shiddah/Rakhawah, Qalqalah).
   - `QuizQuestion.kt`: Multiple-choice models, audio-clip questions, explanation feedback.
2. **`data/`**:
   - `TajweedRepository.kt`: Rich dataset covering all classical Tajweed science rules with verified Arabic texts, Diacritics, and audio clips.
   - `local/`: Room database with entities and DAOs for offline bookmarks and completed lessons.
3. **`audio/`**:
   - `TajweedAudioPlayer.kt`: Robust coroutine-friendly audio player managing playback, state events (Playing, Buffering, Paused, Idle), and error handling.
4. **`ui/`**:
   - `screens/`: `RulesScreen`, `RuleDetailScreen`, `MakharijScreen`, `RecitationScreen`, `QuizScreen`.
   - `components/`: `TajweedText` (annotated string color highlighter), `AudioPlayPill`, `IslamicPatternDecor`, `MakhrajVisualizer`, `TajweedLegendSheet`.
   - `theme/`: Emerald-and-gold color system, typography with Amiri Arabic font, custom shapes.
