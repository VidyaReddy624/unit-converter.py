# 🔁 Unit Converter

A command-line unit converter written in pure Python — **no external
dependencies**. Convert between units of length, weight, volume, time,
and temperature.

## Features

- 📏 **Length** — mm, cm, m, km, inches, feet, yards, miles
- ⚖️ **Weight** — mg, g, kg, oz, lb, ton, tonne
- 🧪 **Volume** — ml, l, cup, tbsp, tsp, gallon, quart, pint, fl oz
- ⏱️ **Time** — ms, s, min, hour, day, week
- 🌡️ **Temperature** — Celsius, Fahrenheit, Kelvin (proper formula-based conversion, not just multiplication)
- Case-insensitive unit names, with common aliases (`km` / `kilometer` / `kilometers`)
- Clear error messages for invalid or incompatible units (e.g. converting km to kg)
- Interactive mode for converting multiple values in a row
- Single-shot command-line mode for quick lookups or scripting

## Installation

```bash
git clone https://github.com/<your-username>/unit-converter.git
cd unit-converter
```

No `pip install` needed. Requires Python 3.8+.

## Usage

### Single conversion

```bash
python unit_converter.py <value> <from_unit> <to_unit>
```

Examples:
```bash
python unit_converter.py 10 km miles
# 10.0 km = 6.21371 miles

python unit_converter.py 100 celsius fahrenheit
# 100.0 celsius = 212 fahrenheit

python unit_converter.py 2.5 gal l
# 2.5 gal = 9.46353 l
```

### List available units

```bash
python unit_converter.py --list length
# length: mm, cm, m, km, in, ft, yd, mi
```

### Interactive mode

Run with no arguments to enter interactive mode:

```bash
python unit_converter.py
```
```
Unit Converter (interactive mode). Type 'quit' to exit, 'units' to list units.

Convert (e.g. '10 km m'): 5 kg lb
  -> 5.0 kg = 11.0231 lb

Convert (e.g. '10 km m'): units
Available units by category:
  length       mm, cm, m, km, in, ft, yd, mi
  weight       mg, g, kg, oz, lb, ton, tonne
  ...

Convert (e.g. '10 km m'): quit
```

### Error handling

Converting between incompatible categories (e.g. length to weight) gives
a clear error instead of a silent wrong answer:

```bash
python unit_converter.py 1 km kg
# Error: Cannot convert between incompatible units: 'km' (length) and 'kg' (weight)
```

## Project structure

```
unit-converter/
├── unit_converter.py         # CLI (single-shot + interactive modes)
├── converter.py               # Core conversion logic (all math/lookup tables)
├── tests/
│   └── test_converter.py     # 29 unit tests
├── .github/workflows/ci.yml  # CI: run tests on push/PR
├── .gitignore
├── LICENSE
└── README.md
```

The conversion math is kept entirely separate from the CLI, so it's
fully unit-testable without any input/output involved.

## Running tests

```bash
pip install pytest
pytest tests/ -v
```

## How the conversions work

- For length, weight, volume, and time, each unit has a fixed
  multiplier relative to a base unit (metres, grams, litres, and
  seconds respectively). Converting is: `value × from_factor ÷ to_factor`.
- Temperature isn't linear through zero, so it's handled with the
  standard formulas, converting through Celsius as an intermediate step.

## Roadmap ideas

- [ ] Add area and speed categories
- [ ] Support unit abbreviation autocomplete/suggestions on typo
- [ ] Add a `--precision` flag to control decimal places
- [ ] Batch conversion from a CSV file

## Contributing

Issues and pull requests are welcome. Please run `pytest` before submitting.

## License

MIT — see [LICENSE](LICENSE).
