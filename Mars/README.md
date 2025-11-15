# Mars - Software Architecture Exercises

Professional software architecture analysis demonstrating SOLID principles, dependency management, and clean architecture patterns through three real-world case studies.

## Exercises

### 1. Charts/Products Architecture Analysis
**Exercise ID:** ArchitecturalQuality10

[Read full analysis →](01-architecture-real-life-story/architectural-principles-analysis.md)

**Problem:** A legacy system with mixed responsibilities (charts + financial logic) and duplicated code across products.

**What you'll learn:**
- Identifying architectural smells: SRP, CCP, DIP, SDP, SAP violations
- Refactoring to clean separation with stable abstractions
- Arrow Legend: Dark blue (normal dependencies) vs orange dashed (violations)

### 2. Climate Model Architecture Analysis
**Exercise ID:** ArchitecturalQuality08

[Read full analysis →](02-climate-model-analysis/climate-model-analysis.md)

**Problem:** A climate model system with 9 components exhibiting unstable dependencies and high change rates.

**What you'll learn:**
- Change frequency analysis (1x to 150x changes/year)
- Detecting SDP violations (stable→volatile dependencies)
- Impact analysis of architectural weaknesses
- Arrow Legend: Dark blue (normal dependencies) vs orange dashed (violations)

### 3. Mars Moons Application Core
**Exercise ID:** Mars02

[Read full design →](03-mars-moons-application-core/application-core-design.md)

**Problem:** Calculate joint visibility time of Mars moons (Deimos and Phobos) with clean architecture.

**What you'll learn:**
- Stateless component design with pure functions
- Single responsibility principle in practice
- 4-layer pipeline architecture (Parser → Normalizer → Calculator → Extractor)
- Handling Mars-specific time system (25h × 100min/day)

---

## Directory Structure

```bash
Mars/
├── README.md                                  # This file
├── CLAUDE.md                                  # Clean Markdown refactoring guide
├── Mars.csproj                                # Project file
├── 01-architecture-real-life-story/
│   ├── architectural-principles-analysis.md   # SOLID principles violations & fixes
│   └── class-group-exercise-architecture-real-life-story.pdf
├── 02-climate-model-analysis/
│   ├── climate-model-analysis.md              # Stability & dependency analysis
│   └── group-exercise-climate-model.pdf
└── 03-mars-moons-application-core/
    ├── application-core-design.md             # Clean architecture pipeline
    └── home-exercise-and-case-study.pdf
```

## Key Learning Outcomes

- **Architectural Principles:** SRP, CCP, CRP, OCP, DIP, SDP, SAP
- **Dependency Management:** Stable dependencies, change frequency analysis, SDP violations
- **Application Core Design:** Component decomposition, stateless design, pure functions
- **Domain Modeling:** Mars time system (25h × 100min/day), interval calculations, edge cases
- **C4 Diagrams:** System visualization with Mermaid (GitHub-native rendering)

---

Quick run from repository root

- Activate your Python venv at the repository root, then run:
  - python3 mars_moon_core.py
  - or run tests: (from Mars/03-mars-moons-application-core) python3 -m unittest -v

Notes

- The actual implementation lives under 03-mars-moons-application-core. A small root-level shim (mars_moon_core.py) delegates to that file so the above command works from the repository root.
- Because the root shim shares the same module name, run `python -m unittest` from inside `03-mars-moons-application-core` (or set `PYTHONPATH` accordingly) so tests import the real module rather than the shim.

One-time automatic Python setup (no manual clicking in Rider)

If you want this to be fully automatic per solution folder, run this once from the repository root:

- python3 setup-python-venv.py Mars/03-mars-moons-application-core
- or (if executable) ./setup-python-venv Mars/03-mars-moons-application-core

This creates Mars/03-mars-moons-application-core/venv using your current Python. After that you can either:
- source Mars/03-mars-moons-application-core/venv/bin/activate
- or in Rider/PyCharm, select the interpreter at Mars/03-mars-moons-application-core/venv/bin/python3

Tip: The root shim mars_moon_core.py will also auto-create that venv on first run if it’s missing.

Rider run configuration (shared)

- `.run/python3.14.run.xml` is checked in and already points to `$PROJECT_DIR$/Mars/03-mars-moons-application-core/venv/bin/python3`.
- Open **Run | Run…** and choose `python3.14` – Rider does not ask you to pick a module anymore because the interpreter and working directory are pre-wired.
- For any new `.sln`/solution folder, run `python3 setup-python-venv.py <path-to-solution>` once and copy the `.run` template if you want the same zero-click interpreter wiring.
- Upgrading to the newest Homebrew/Python.org build is just `brew upgrade python` (or installer) followed by `python3 setup-python-venv.py Mars/03-mars-moons-application-core --recreate` to rebuild the venv so every new `.sln` can reuse the same automation.
