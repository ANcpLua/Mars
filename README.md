# Mars Moon Visibility Calculator

A Python application that calculates joint visibility windows for Mars' moons Deimos and Phobos.

## Requirements

- Python 3.9 or higher (tested with Python 3.14)
- No external dependencies (uses only Python standard library)

## Quick Start

1. Clone this repository
2. Run the application:

```bash
python mars_moon_core.py
```

The wrapper script will automatically:
- Create a virtual environment in `Mars/03-mars-moons-application-core/venv/`
- Run the Mars Moon Core application
- Display example calculations

## How It Works

The application calculates when both Deimos and Phobos are simultaneously visible from Mars' surface. It handles:

- Mars time system (25-hour days, 100-minute hours)
- Wraparound across midnight
- Joint visibility overlap calculation
- Twilight rule (1 minute when moons touch but don't overlap)

## Example Output

```
Example 1: D[13:91, 23:05], P[22:05, 24:45] -> 100
Example 2: D[24:53, 7:12],  P[5:12, 8:45]   -> 200
Example 3: D[12:32, 17:06], P[17:06, 19:78] -> 1
Example 4: D[5:00, 6:00],    P[7:00, 8:00]  -> 0
Example 5: D[10:00, 25:00],  P[0:00, 5:00]  -> 1
```

## Project Structure

```
Mars/
├── mars_moon_core.py                     # Wrapper script (run this)
├── Mars/03-mars-moons-application-core/
│   ├── mars_moon_core.py                # Application core
│   ├── test_mars_moon_core.py           # Test suite
│   ├── requirements.txt                 # Empty (no deps needed)
│   └── README.md                        # Detailed documentation
```

## Running Tests

```bash
cd Mars/03-mars-moons-application-core
python -m pytest test_mars_moon_core.py
```

## Architecture

The application is structured as a pure functional core with four components:

- **Component A**: Parse input timestamps
- **Component B**: Normalize to Mars time intervals
- **Component C**: Calculate geometric overlap
- **Component D**: Apply twilight rule and extract duration

See `Mars/03-mars-moons-application-core/README.md` for detailed architecture documentation.
