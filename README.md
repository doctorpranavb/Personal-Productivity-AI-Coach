# Personal Productivity AI Coach

### Turning personal activity data into structured AI-assisted reflection and behavioral coaching during USMLE preparation

*RescueTime API integration · multi-LLM experimentation · behavioral metrics · context-aware coaching · AI-assisted development*

> **Portfolio case study. Source code, internal prompts, API configuration, and implementation details are intentionally private.**

I built **Personal Productivity AI Coach** during USMLE preparation as my first experiment with the RescueTime API — before several of my later study-productivity tools.

The idea came from a simple observation:

**RescueTime could tell me what I was doing. I wanted another layer to help me think about what those patterns meant.**

I had also spent years reading authors such as Brian Klemmer, including *The Compassionate Samurai*, and was interested in the difference between receiving information and being actively coached. A dashboard can report behavior. A coach can interpret it, challenge it, reframe it, and ask what should change next.

This project was my attempt to explore that difference using my own activity data.

<p align="center">
  <img src="media/01_ai-coach_browser-context_portfolio.png" alt="Personal Productivity AI Coach running beside a live browser workflow" width="900"/>
</p>

---

## At a Glance

| | |
|---|---|
| **Interface** | Browser-side slide-in productivity coaching panel |
| **Trigger** | `Option + A` to open or close the coach |
| **Measurement layer** | RescueTime activity data |
| **Time windows** | Today · 7 Days · This Month |
| **Historical AI providers tested** | Groq · Mistral · NVIDIA · Cohere · Gemini |
| **Coaching modes** | Deep Hourly · Summary · Enterprise · World Class |
| **Example computed signals** | Deep-work ratio · fragmentation index · longest productive block · peak/worst periods · context-switch patterns |
| **Interaction** | Structured coaching output plus follow-up questions about the same activity data |

### Conceptually

**RescueTime activity data → structured behavioral metrics → selected coaching lens → AI interpretation → actionable reflection**

This was a personal experimentation project, not a validated psychological, clinical, or productivity-assessment instrument.

---

## Why I Built It

Productivity dashboards are useful, but they still leave the user with the work of interpretation.

I wanted to explore questions such as:

- Was I actually doing sustained work, or merely accumulating scattered productive minutes?
- Was an apparently productive application helping the main goal or competing with it?
- At what times was my attention fragmenting most?
- Were there patterns in the data that were not obvious from a daily total?
- What should I change in the next study session rather than simply observe?

The missing layer, for me, was **interpretation**.

RescueTime served as the measurement layer. The AI Coach was an experimental interpretation layer built on top of it.

---

## From Activity Data to Coaching

After selecting a time window and analysis mode, the tool transformed activity data into a set of structured productivity signals before passing a summarized behavioral picture to the selected AI provider.

The interface surfaced metrics such as:

- deep-work ratio
- fragmentation / context-switching
- longest productive block
- productive versus distracting activity
- peak and low-performing periods
- application-level patterns

<p align="center">
  <img src="media/02_ai-coach_metrics-and-coaching_portfolio.png" alt="Computed productivity metrics and AI coaching output" width="720"/>
</p>

The point was not to treat one score as absolute truth.

The metrics gave the model a more structured picture than a raw list of applications and durations, allowing the response to move from:

**“What did I use?”**

toward:

**“What pattern does this activity suggest?”**

---

## Beyond Summarizing the Data

One of the parts I found most interesting was the **HIDDEN PATTERN** section.

A low productivity percentage alone is not especially insightful. But combining several signals — for example, very short productive sessions, a high level of switching, and the absence of a sustained productive block — can reveal something qualitatively different about how the day unfolded.

The coach attempted to surface those less-obvious patterns and then translate them into specific next actions.

<p align="center">
  <img src="media/03_ai-coach_insight-to-action_portfolio.png" alt="Hidden Pattern and Your 3 Moves coaching sections" width="720"/>
</p>

That distinction became central to the project:

**A dashboard reports. A coach interprets, challenges, reframes, and asks what should change next.**

---

## Multiple Coaching Lenses

As the project evolved, I realized that one style of analysis could not answer every productivity question well.

I therefore experimented with four different coaching lenses:

- **Deep Hourly** — more granular examination of activity, productive periods, and fragmentation
- **Summary** — a concise synthesis of the period with key patterns and actionable moves
- **Enterprise** — a more operational lens focused on recurring friction, allocation, and systemic patterns
- **World Class** — an experimental performance-oriented lens that drew on named productivity and performance frameworks

<p align="center">
  <img src="media/04_ai-coach_analysis-section-sampler_portfolio.png" alt="Representative sections from Deep Hourly, Summary, Enterprise, and World Class coaching modes" width="900"/>
</p>

The modes deliberately emphasized different questions while operating on the same underlying behavioral record.

The **World Class** mode was exploratory. Some outputs referenced external authors, research concepts, organizations, or numerical benchmarks supplied through the coaching prompt. I do **not** present those generated comparisons as independently validated performance standards; they were part of an experiment in how different prompt lenses changed interpretation.

---

## Multi-Provider Experimentation

The project also became an experiment in working across multiple AI APIs.

At different stages, I tested providers including:

- Groq
- Mistral
- NVIDIA
- Cohere
- Gemini

This was useful because models differed in output style, practical limits, reliability, and how well they handled the structured activity summaries I was generating.

Provider availability and free-tier endpoints changed over time, so the models visible in the screenshots represent the project **at that stage of development**, not a claim about what is currently available.

Gemini became particularly useful during my own later testing because it was practical for producing longer structured coaching responses within the access available to me at the time.

---

## The Most Interesting Insight: AI Could Itself Become the Distraction

One of the most memorable patterns surfaced by the project was an uncomfortable one:

**AI use could look productive while still displacing the work I had actually intended to do.**

Reading, experimenting, prompting, and building could all feel intellectually productive. But during dedicated exam preparation, the relevant question was not whether an activity was interesting or useful in isolation.

The question was:

**Was it helping the primary goal at that moment?**

The coach repeatedly surfaced periods in which extensive AI-tool use competed with direct engagement with my core study material.

That created an interesting irony: an AI-based coaching system was helping expose excessive AI use.

<p align="center">
  <img src="media/05_ai-coach_personal-coaching-identity_portfolio.png" alt="Coach's Corner showing the project's more direct coaching style" width="720"/>
</p>

The observations reinforced a broader change in how I managed my environment. I increasingly relied on stronger distraction controls, including Cold Turkey and Micro Manager, and made my study routine more structured.

As that environment became more consistent, I used the AI Coach less frequently.

That progression became one of the most useful lessons from the project:

**awareness → interpretation → coaching → environmental control → routine**

The goal was never permanent dependence on an AI coach.

A better outcome was reaching the point where I needed it less.

---

## How It Evolved

<details>
<summary><strong>Development story</strong></summary>

This was the first RescueTime/API tool I built.

It preceded my later Review Timer, Test Timer, QBank productivity tools, and Personal Focus Pattern Explorer.

At that stage, I did not yet have access to the more capable agentic coding workflows I use today. I built the project through repeated cycles of:

- defining a feature or behavior I wanted
- prompting earlier AI coding models
- reading and checking the generated implementation
- testing it against real RescueTime data
- finding failures and edge cases
- describing corrections
- retesting
- gradually expanding the tool

The early versions were much simpler.

Over time, the project accumulated:

- RescueTime API integration
- several data views and activity summaries
- calculated behavioral metrics
- Today / 7 Days / This Month analysis
- multiple coaching modes
- several AI-provider integrations
- structured mode-specific responses
- model switching
- follow-up questions against the same personal activity context
- loading, retry, and error-handling behavior
- substantial interface refinement

The system also required maintenance because model names, endpoints, free-tier limits, and provider availability changed.

Eventually, the practical need for the coach itself decreased. Stronger environmental controls and a more repeatable study routine reduced the amount of interpretation I needed from an external system.

That was not a failure of the project. In many ways, it was the desired endpoint.

</details>

---

## AI-Assisted Development

This project was created with **substantial AI coding assistance**.

I did not hand-code the entire application from scratch, and I do not present it that way.

My role centered on:

- identifying the problem
- defining the desired behavior and coaching experience
- specifying features and interface changes
- iteratively prompting AI systems to generate and revise code
- testing the system against real personal data
- identifying bugs and weak outputs
- finding edge cases
- specifying corrections
- comparing alternative implementations
- repeatedly validating and refining the result

At the time this project began, I had basic programming experience but did not yet have access to the modern agentic coding tools I later used.

For me, the project represents **AI-assisted software development driven by problem definition, experimentation, testing, debugging, and iterative refinement**.

---

## What It Taught Me

The technical experiment was interesting, but several broader lessons mattered more.

### Data is not the same as understanding

Collecting more metrics does not automatically create better decisions. The useful step is deciding what a measurement means in the context of the actual goal.

### Interpretation should remain challengeable

AI-generated explanations can sound authoritative even when the underlying inference is uncertain. I learned to treat the coaching as a prompt for reflection rather than as an unquestionable diagnosis of behavior.

### Environment can outperform motivation

Once the largest distraction pathways were aggressively restricted, maintaining focus required less repeated coaching.

### Tools can become avoidance mechanisms

A sophisticated productivity system can itself become another project to optimize. At some point, the correct action is to stop improving the system and do the work it was built to support.

---

## What This Project Demonstrates

Beyond the productivity use case, this project reflects the way I tend to approach practical problems:

1. notice friction in an existing workflow;
2. identify what information is missing;
3. ask whether data can make the problem more visible;
4. prototype a tool;
5. use it in a real setting;
6. challenge the output rather than accepting it blindly;
7. refine what works;
8. discard what no longer adds value.

The value of the project, for me, is not any individual AI-generated recommendation.

It is the process of turning a personal problem into something **measurable, testable, interpretable, and improvable**.

---

## Project Status

This repository is a **portfolio case study**.

The production source code is intentionally private.

Not included publicly:

- API credentials or configuration
- internal prompts
- provider-routing logic
- metric formulas
- thresholds and scoring logic
- preprocessing architecture
- detailed RescueTime API handling
- private activity data beyond the selected portfolio examples

The screenshots demonstrate the user-facing behavior and development outcome without publishing the implementation required to reproduce the system.

This project is not currently distributed as a public application.

---

## Author

**Pranav Krishna Buddhapuram**

Orthopaedic surgeon with interests in medical education, research, productivity systems, data-informed self-improvement, and practical AI-assisted software development.

---

## Intellectual Property

© 2026 Pranav Krishna Buddhapuram. All rights reserved.

This repository is provided for portfolio and demonstration purposes only.

No license is granted to reproduce, distribute, modify, commercialize, reverse engineer, or create derivative implementations from the materials presented here.
