# Mars - Software Architecture Exercises

Professional software architecture analysis demonstrating SOLID principles, dependency management, and clean architecture patterns through three real-world case studies.

Part of the Software Architecture course exercise collection.

## Table of Contents

- [Exercises](#exercises)
- [Running the Code](#running-the-code)
- [Directory Structure](#directory-structure)
- [Key Learning Outcomes](#key-learning-outcomes)

## Exercises

### Exercise 0: Architectural Decisions and Quality Attributes
**Type:** Class Group Exercise | **Topic:** Decision-Making

**Problem:** Which architectural decisions are hard to change, and which quality attributes do they impact most?

**What you'll learn:**
- Relationship between architectural decisions and non-functional requirements
- How decisions impact multiple quality attributes simultaneously
- Why architects are requirements engineers for non-functional requirements
- Which "-ility" (changeability, efficiency, security, etc.) appears most frequently

**Files:**
- [Exercise Overview](00-architectural-decisions-exercise/README.md)
- [Slide Images](00-architectural-decisions-exercise/)

**Key Insight:** Architectural decisions often influence non-functional aspects of software. This is why architects often are the requirements engineers for non-functional requirements.

---

### Exercise 1: Charts/Products Architecture Analysis
**Exercise ID:** ArchitecturalQuality10 | **Evening:** 2 | **Type:** Group

**Problem:** Legacy system with mixed responsibilities (charts + financial logic) and duplicated code across products.

**What you'll learn:**
- Identifying architectural smells: SRP, CCP, DIP, SDP, SAP violations
- Refactoring to clean separation with stable abstractions
- Arrow Legend: Dark blue (normal dependencies) vs orange dashed (violations)

**Files:**
- [Architecture Analysis](01-architecture-real-life-story/architectural-principles-analysis.md)
- [Exercise PDF](01-architecture-real-life-story/class-group-exercise-architecture-real-life-story.pdf)

---

### Exercise 2: Climate Model Architecture Analysis
**Exercise ID:** ArchitecturalQuality08 | **Evening:** 2 | **Type:** Group

**Problem:** Climate model system with 9 components exhibiting unstable dependencies and high change rates.

**What you'll learn:**
- Change frequency analysis (1x to 150x changes/year)
- Detecting SDP violations (stable→volatile dependencies)
- Impact analysis of architectural weaknesses
- Arrow Legend: Dark blue (normal dependencies) vs orange dashed (violations)

**Files:**
- [Climate Model Analysis](02-climate-model-analysis/climate-model-analysis.md)
- [Exercise PDF](02-climate-model-analysis/group-exercise-climate-model.pdf)

---

### Exercise 3: Mars Moons Application Core
**Exercise ID:** Mars02 | **Evening:** 3 | **Type:** Home

**Problem:** Calculate joint visibility time of Mars moons (Deimos and Phobos) with clean architecture.

**What you'll learn:**
- Stateless component design with pure functions
- Single Responsibility Principle in practice
- 4-layer pipeline architecture (Parser → Normalizer → Calculator → Extractor)
- Handling Mars-specific time system (25h × 100min/day)

**Files:**
- [Application Core Design](03-mars-moons-application-core/README.md)
- [Implementation](03-mars-moons-application-core/mars_moon_core.py)
- [Tests](03-mars-moons-application-core/test_mars_moon_core.py)

> [!TIP]
> Complete Mars02 (Exercise 3) before EarlyBird12. The small application core principles demonstrated here apply directly to larger systems.

---

## Running the Code

**Mars Moon Calculator (Exercise 3):**

```bash
# From repository root
python mars_moon_core.py

# Or from exercise directory
cd 03-mars-moons-application-core
python mars_moon_core.py
```

**Requirements:**
- Python 3.9 or higher
- No external dependencies (uses only Python standard library)

**Running Tests:**

```bash
cd 03-mars-moons-application-core
python -m pytest test_mars_moon_core.py
```

> [!NOTE]
> The wrapper script at repository root automatically creates a virtual environment if needed.

## Directory Structure

```
Mars/
├── README.md                                  # This file
├── mars_moon_core.py                          # Wrapper script
├── 00-architectural-decisions-exercise/
│   ├── README.md                              # Exercise overview
│   ├── slide_architectural_decisions_01.png   # Exercise slide
│   └── slide_architectural_decisions_02.png   # Exercise slide (duplicate)
├── 01-architecture-real-life-story/
│   ├── architectural-principles-analysis.md   # ArchitecturalQuality10
│   └── class-group-exercise-architecture-real-life-story.pdf
├── 02-climate-model-analysis/
│   ├── climate-model-analysis.md              # ArchitecturalQuality08
│   └── group-exercise-climate-model.pdf
└── 03-mars-moons-application-core/
    ├── README.md                              # Detailed architecture docs
    ├── mars_moon_core.py                      # Mars02 implementation
    ├── test_mars_moon_core.py                 # Test suite
    └── home-exercise-and-case-study.pdf
```

## Key Learning Outcomes

**Architectural Principles:**
- SRP (Single Responsibility Principle)
- CCP (Common Closure Principle)
- CRP (Common Reuse Principle)
- OCP (Open-Closed Principle)
- DIP (Dependency Inversion Principle)
- SDP (Stable Dependencies Principle)
- SAP (Stable Abstractions Principle)

**Skills:**
- Architectural decision analysis and impact assessment
- Non-functional requirements engineering
- Dependency management and stability analysis
- Change frequency analysis
- Application core design with pure functions
- Domain modeling (Mars time system: 25h × 100min/day)
- Component decomposition
- Stateless design patterns
