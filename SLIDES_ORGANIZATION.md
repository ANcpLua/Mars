# Exercise Slides Organization

This document describes the standardized slide organization structure across all Software Architecture course repositories.

## Structure Convention

Each exercise folder contains a `slides/` subdirectory with:
- **README.md** - Exercise context, slide descriptions, and key learning points
- **Slide images** - PNG/JPG files named according to convention

## Naming Convention

Slide images follow this pattern:
```
slide_{exercise_id}.png
slide_{exercise_id}_{sequence_number}.png
```

Examples:
- `slide_architecturalquality03.png`
- `slide_mars02_01.png`
- `slide_mars02_02.png`

## Repository Organization

### Mars Repository

```
Mars/
├── 00-architectural-decisions-exercise/
│   ├── README.md
│   ├── slide_architectural_decisions_01.png
│   └── slide_architectural_decisions_02.png
│
├── 01-architecture-real-life-story/
│   └── slides/
│       ├── README.md
│       └── slide_architecturalquality10.png
│
├── 02-climate-model-analysis/
│   └── slides/
│       ├── README.md
│       └── slide_architecturalquality08.png
│
└── 03-mars-moons-application-core/
    └── slides/
        ├── README.md
        ├── slide_mars02_01.png
        ├── slide_mars02_02.png
        └── slide_mars02_03.png
```

### EarlyBird Repository

```
EarlyBird/
├── 01-isearchproduct-specification/
│   └── slides/
│       ├── README.md
│       └── slide_architecturalquality03.png
│
├── 02-interface-quality-review/
│   └── slides/
│       ├── README.md
│       └── slide_architecturalquality04.png
│
├── 03-ilist-interface-design/
│   └── slides/
│       ├── README.md
│       └── slide_architecturalquality07.png
│
└── 04-application-core-architecture/
    └── slides/
        ├── README.md
        └── slide_earlybird12.png
```

### MateMate Repository

```
MateMate/
└── exercises/
    └── MateMate02-service-based-architecture/
        └── slides/
            ├── README.md
            ├── slide_matemate02_01.png
            └── slide_matemate02_02.png
```

## Benefits of This Structure

1. **Consistency** - Same pattern across all repos
2. **Discoverability** - Slides live with their exercises
3. **Documentation** - README explains context and learning goals
4. **Separation** - Slide images separate from exercise solutions
5. **Maintenance** - Easy to update slides independently

## Adding New Slides

When adding slide images:

1. Place PNG/JPG files in the appropriate `slides/` folder
2. Follow the naming convention
3. Update the `slides/README.md` if needed
4. Ensure images are appropriately sized (recommend max 1920px width)

## Exercise-to-Slide Mapping

| Exercise ID | Repository | Slides | Description |
|-------------|------------|--------|-------------|
| Evening 1 Exercise | Mars | 2 slides | Architectural Decisions |
| ArchitecturalQuality03 | EarlyBird | 1 slide | ISearchProduct Interface |
| ArchitecturalQuality04 | EarlyBird | 1 slide | Interface Quality Checklist |
| ArchitecturalQuality07 | EarlyBird | 1 slide | IList Interface Review |
| ArchitecturalQuality08 | Mars | 1 slide | Climate Model Analysis |
| ArchitecturalQuality10 | Mars | 1 slide | Charts/Products Architecture |
| MateMate02 | MateMate | 2 slides | Service-Based Architecture |
| Mars02 | Mars | 3 slides | Mars Moons Application Core |
| EarlyBird12 | EarlyBird | 1 slide | EarlyBird Application Core |

## Notes

- Some exercises (ArchitecturalQuality09 - Heat Flow Calculator) may not have dedicated slide images
- Exercises may reference PDFs for detailed content
- Slide images are quick references; full exercise content is in markdown files
