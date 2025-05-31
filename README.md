# 🧩 DEF to VCMI JSON Converter

This tool converts **Heroes of Might and Magic III `.def` files** into a format compatible with **VCMI**. It extracts all image frames (normal, shadow, overlay) and generates a `.json` metadata file usable by VCMI mods.

---

## 🔧 Features

- Extracts all images from `.def` files (normal, shadow, overlay)
- Saves each frame as a `.png` file
- Generates a `.json` file with metadata in VCMI format
- Supports:
  - GUI-based file selection (for quick use)
  - Command-line usage for automation and scripting
  - Optional standalone executable (no Python required)

---

## 🚀 Usage

### Option 1: GUI mode

Run:

```bash
python de2json.py
```

Select one or more `.def` files using the file dialog. The tool will:

- Create a subfolder with extracted PNGs (named after the `.def` file)
- Generate a `.json` file in the same directory

### Option 2: Command-line mode

```bash
python de2json.py path/to/file.def [another.def ...]
```

This will process the provided `.def` files directly, without showing any GUI.

---

## 📁 Output Structure

For a file named `example.def`, this tool will create:

```
example/                 # Folder with all image frames
  frame1.png
  frame1-shadow.png
  frame1-overlay.png
  ...
example.json             # JSON metadata for VCMI
```

---

## 📦 Using in VCMI

To use in a VCMI mod:

1. Copy the `example/` folder and `example.json` into the `sprites/` folder of your mod.
2. If placing inside a subfolder (e.g. `sprites/myfolder/example/`), update the `basepath` in the `.json` accordingly:

```json
{
    "basepath": "myfolder/example/",
    ...
}
```

---

## 📥 Requirements

You can use this tool in two ways:

### ✅ Option 1: Python script

- Requires Python 3
- Install dependencies from `requirements.txt`:

```bash
pip install -r requirements.txt
```

Then run:

```bash
python de2json.py
```

### ✅ Option 2: Standalone executable

If you don't have Python installed, use the provided standalone executable:

- No installation needed
- Just double-click or run from command line:

```bash
./de2json.exe          # on Windows
./de2json              # on Linux/
```


