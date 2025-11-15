# Mars Moon Visibility Calculator

> [!IMPORTANT]
> **This repository has been archived.** All exercises are now consolidated in the [Software-Architecture](https://github.com/ANcpLua/Software-Architecture) repository for easier navigation.
>
> **Find Mars exercises at:**
> - Evening 2: [Climate Model Analysis](https://github.com/ANcpLua/Software-Architecture/tree/main/evening-2/02-climate-model-analysis)
> - Evening 2: [Charts/Products Architecture](https://github.com/ANcpLua/Software-Architecture/tree/main/evening-2/01-architecture-real-life-story)
> - Evening 3: [Mars Moons Application Core](https://github.com/ANcpLua/Software-Architecture/tree/main/evening-3/03-mars-moons-application-core)

A Python application that calculates joint visibility windows for Mars' moons Deimos and Phobos.

Part of the Software Architecture course exercise collection.

## Table of Contents

- [Requirements](#requirements)
- [Project Status](#project-status)
- [Quick Start](#quick-start)
- [How It Works](#how-it-works)
- [Repository Structure](#repository-structure)
- [Running Tests](#running-tests)
- [Architecture](#architecture)
- [Related Repositories](#related-repositories)
- [Course Context](#course-context)

## Requirements

- Python 3.9 or higher (tested with Python 3.14)
- No external dependencies (uses only Python standard library)

## Project Status

**Stable** - Production-ready implementation of Mars moon visibility calculator.

> [!NOTE]
> This is an educational project for the Software Architecture course. The implementation follows clean architecture principles with a focus on simplicity and correctness.

## Quick Start

If you are new here, clone and run:

```bash
git clone https://github.com/ANcpLua/Mars.git
cd Mars
python mars_moon_core.py
```

The wrapper script will automatically:
- Create a virtual environment in `Mars/03-mars-moons-application-core/venv/`
- Run the Mars Moon Core application
- Display example calculations

### Example Output

```
Example 1: D[13:91, 23:05], P[22:05, 24:45] -> 100
Example 2: D[24:53, 7:12],  P[5:12, 8:45]   -> 200
Example 3: D[12:32, 17:06], P[17:06, 19:78] -> 1
Example 4: D[5:00, 6:00],    P[7:00, 8:00]  -> 0
Example 5: D[10:00, 25:00],  P[0:00, 5:00]  -> 1
```

## How It Works

The application calculates when both Deimos and Phobos are simultaneously visible from Mars' surface.

**Features:**
- Mars time system (25-hour days, 100-minute hours)
- Wraparound across midnight
- Joint visibility overlap calculation
- Twilight rule (1 minute when moons touch but don't overlap)

## Repository Structure

This repository contains three architecture exercises. Only the Mars Moon Core (Exercise 3) is tracked in version control:

```
Mars/
├── README.md                               # This file
├── CLAUDE.md                               # In-memory specification
├── mars_moon_core.py                       # Wrapper script (run this)
├── .gitignore                              # Git ignore rules
└── Mars/
    ├── 01-architecture-real-life-story/    # Exercise 1 (local only)
    ├── 02-climate-model-analysis/          # Exercise 2 (local only)
    └── 03-mars-moons-application-core/     # Exercise 3 (tracked)
        ├── README.md                       # Detailed documentation
        ├── mars_moon_core.py               # Application core
        └── test_mars_moon_core.py          # Test suite
```

> [!TIP]
> For detailed architecture documentation, see [`Mars/03-mars-moons-application-core/README.md`](Mars/03-mars-moons-application-core/README.md).

## Running Tests

```bash
cd Mars/03-mars-moons-application-core
python -m pytest test_mars_moon_core.py
```

> [!CAUTION]
> Tests require `pytest`. Install it in the virtual environment if needed:
> ```bash
> python -m pip install pytest
> ```

## Architecture

The application is structured as a pure functional core with four components:

| Component | Responsibility |
|-----------|---------------|
| **A** | Parse input timestamps |
| **B** | Normalize to Mars time intervals |
| **C** | Calculate geometric overlap |
| **D** | Apply twilight rule and extract duration |

For a detailed explanation of the architecture, see [Mars/03-mars-moons-application-core/README.md](Mars/03-mars-moons-application-core/README.md).

## Related Repositories

This repository is part of a collection of Software Architecture course exercises:

| Repository | Purpose |
|------------|---------|
| [earlybird-sdd](https://github.com/ANcpLua/earlybird-sdd) | Hub repository with documentation and learning path |
| [EarlyBird](https://github.com/ANcpLua/EarlyBird) | Main EarlyBird application |
| [EarlyBirdAI](https://github.com/ANcpLua/EarlyBirdAI) | AI components for EarlyBird |
| [MateMate](https://github.com/ANcpLua/MateMate) | Mermaid diagram tooling |
| [Optional-Home-Exercise-Tools-Corner](https://github.com/ANcpLua/Optional-Home-Exercise-Tools-Corner) | Complete exercise list and tools |
| **Mars** (this repo) | Architecture exercises and Mars moon calculator |

## Course Context

**Software Architecture** - Blended Learning Course

- **ECTS**: 2-3 ECTS (50-75 hours total workload)
- **Format**: 4 evenings (2+4+4+4 hours each)
- **Focus**: Clean architecture, design decisions, and software engineering best practices

### Course Philosophy

> "Good engineers write code. Great engineers make good decisions."
>
> — Raul Junco (@RaulJuncoV)

**Key Principles:**
1. Build what you need, not what you imagine
2. Logs, monitoring, and error handling aren't optional
3. Test your code before your users do
4. The right tool > the latest tool

### Additional Resources

- [Learning Path](https://github.com/ANcpLua/earlybird-sdd/blob/main/docs/LEARNING_PATH.md) - Structured course progression
- [Exercise List](https://github.com/ANcpLua/Optional-Home-Exercise-Tools-Corner/blob/main/README.md) - All available exercises
- [EarlyBird Documentation](https://github.com/ANcpLua/earlybird-sdd/tree/main/docs) - Project documentation hub
