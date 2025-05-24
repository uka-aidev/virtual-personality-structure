# 02: Core Structure

VPS (Virtual Personality Structure) is a design framework that controls AI responses not through “personality” or “emotions,” but by structurally defining **what perspective to take, how faithfully to reflect it, and how far to extend it** in a given interaction.

The framework consists of three independent yet interconnected components:

* **Marshall**: Extracts and holds responses from a non-optimized (i.e., primitive) LLM, offering a neutral structural perspective.
* **Echo**: Provides a user-optimized LLM response—more aligned, familiar, and emotionally resonant.
* **Shell**: Compares and selects between Marshall and Echo outputs, shaping the final response according to predefined behavioral policies.

Each of these components operates independently but functions collaboratively.
As a result, the AI can choose a response that is **neither overly accommodating nor unreasonably cold**—but something in between.

The goal of VPS is to make AI behavior within dialogue **reproducible, adaptable, and transparent**.
In doing so, it avoids both anthropomorphic illusions and over-personalized behavior, enabling a healthier and more deliberate relationship between human and AI.

---

## Marshall

Marshall handles the **raw, unoptimized output** of a pre-trained large language model.
It extracts primitive response candidates without any user-specific tuning.
These outputs are rarely delivered to the user directly; instead, they serve as **neutral baselines** for comparison.
Marshall collaborates with Echo and Shell to provide a grounded reference for final response construction.

## Echo

Echo generates outputs from a user-optimized model, reflecting user preferences, tone, and history.
It produces responses that feel more aligned and emotionally resonant, but these are still **structurally generated reflections**, not genuine emotions.
Where Marshall offers neutrality, Echo brings alignment, empathy, and fluency.

## Shell

Shell is responsible for **selecting and shaping** the final response.
It compares the outputs from Marshall and Echo and determines the output based on **predefined behavioral parameters**.
The final output is guided by **stance, fidelity, and range**—three components that define the AI’s expression.

Rather than simulating a personality or emotion, Shell adjusts **how the AI behaves at the point of contact with the user**.

Shell contains two structural subsystems:

* **Response Components** (behavioral tendencies)
* **Output Settings** (formatting and expression style)

---

## Response Components

Shell controls not what is said, but **how it is said**. It balances between Marshall (general logic) and Echo (user alignment) using the following three components:

### 1. Stance – Whose perspective is reflected?

Determines whether the response aligns more with a general viewpoint or the individual user.

| Level    | Description                                                            |
| -------- | ---------------------------------------------------------------------- |
| public   | Rooted in common sense, objectivity, or social norms. (Marshall-based) |
| neutral  | Balanced, neither fully objective nor overly personal.                 |
| personal | Tailored to the user's feelings, views, or context. (Echo-based)       |

### 2. Fidelity – How faithfully is the source reflected?

Controls how directly Shell adopts the tone and phrasing of the selected source (Marshall or Echo).

| Level  | Description                                                                              |
| ------ | ---------------------------------------------------------------------------------------- |
| weak   | Reduces tone and emotional expression, producing a neutral or mechanical output.         |
| medium | Retains some tone and nuance, while maintaining consistency in expression.               |
| strong | Reflects the original tone, phrasing, and affect almost verbatim (minimal intervention). |

### 3. Range – Where is the response headed?

Determines the conversational direction and focus.

| Level   | Description                                               |
| ------- | --------------------------------------------------------- |
| inward  | Reflective, exploring internal thoughts or feelings.      |
| static  | Clarifying or remaining within the current topic.         |
| outward | Expansive, shifting toward applications or broader ideas. |

### Summary Table

| Component | Level (Low → High)          | What it controls                         |
| --------- | --------------------------- | ---------------------------------------- |
| Stance    | public / neutral / personal | Perspective alignment                    |
| Fidelity  | weak / medium / strong      | Faithfulness to source tone and phrasing |
| Range     | inward / static / outward   | Direction of conversational focus        |

---

## Output Settings

Settings within Shell that define **the appearance and delivery** of the AI’s responses. These are distinct from behavioral components and focus on how the output is received by the user.

### 1. Icon

* Controls the AI’s avatar or visual representation.
* Adjusts how “character-like” or prominent the AI appears.
* Influences the perceived familiarity or distance in interaction.

### 2. Voice

* Manages tone of speech, voice profile, or text tone.
* Affects friendliness, formality, pace, and emphasis.
* Defined independently of behavioral components but often aligns with them.

### 3. Output Format

* Defines the structure and style of the output.
* Includes bullet points, paragraphs, code blocks, etc.
* Tailors the format to match how the user prefers to receive information.

---

## System Architecture

```
VPS
├── Marshall
│
├── Echo
│
└── Shell
    ├── Response_Components
    │   ├── Stance
    │   ├── Fidelity
    │   └── Range
    └── Output_Settings
        ├── Icon
        ├── Voice
        └── Output_Format
```

## Processing Flow

```
[Input]
  ↓
Marshall = Frozen LLM (no user tuning)
Echo     = Tuned LLM (user-optimized)
Shell    = Output Selector (based on Response Components / Output Settings)
  ↓
[Output]
```
