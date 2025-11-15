# Exercise Slides - Mars02

This folder contains the exercise slides for **Mars02: A Very Small Application Core**.

## Slide Images

Place the following slide images here:

1. `slide_mars02_01.png` - Home Exercise: A Very Small Application Core
   - Shows the 4-component architecture (A → B → C → D)
   - Explains the exercise requirements

2. `slide_mars02_02.png` - Home Exercise: A Very Small Application Core / 2
   - Table for component specification
   - Input/output data structures

3. `slide_mars02_03.png` - Home Exercise: A Very Small Application Core / 3
   - Test case specification table

## Exercise Context

**Exercise ID:** Mars02
**Evening:** 3
**Type:** Home
**PDF:** Pages 222-224 in Architecture Development slides

**Task:** Design a 4-component architecture for calculating joint visibility of Mars moons Deimos and Phobos.

**Components:**
- A: Parser (8 integers → structured windows)
- B: Normalizer (windows → Mars-minute intervals)
- C: Overlap Calculator (intervals → overlap duration)
- D: Duration Extractor (apply twilight rule)
