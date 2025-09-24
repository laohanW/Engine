# Building the Documentation

## Prerequisites
- Doxygen (1.9+ recommended)

## Generate HTML
From the repository root:

```bash
# Install doxygen if needed (Ubuntu/Debian)
sudo apt-get update && sudo apt-get install -y doxygen

# Generate docs
mkdir -p docs/build
doxygen Doxyfile

# Open docs/build/html/index.html in a browser
```

## Inputs
- Source headers under `Runtime/` and `Platform/`
- Markdown guides under `docs/`

The main landing page is `docs/README.md`.
