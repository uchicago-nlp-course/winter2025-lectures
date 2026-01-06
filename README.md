# CMSC 25700/35100: Natural Language Processing

**Instructor:** Chenhao Tan
**Quarter:** Winter 2025
**University of Chicago**

## Overview

This repository contains lecture slides for the Natural Language Processing course taught at the University of Chicago. The slides are built using [reveal.js](https://revealjs.com/), a framework for creating presentations using HTML.

## Viewing the Slides

### Online (GitHub Pages)

Once deployed to GitHub Pages, the slides will be available at:
```
https://uchicago-nlp-course.github.io/winter2025-lectures/
```

### Local Development

1. Clone this repository:
```bash
git clone https://github.com/uchicago-nlp-course/winter2025-lectures.git
cd winter2025-lectures
```

2. Open the main index page or individual lecture slides in your web browser:
```bash
# open a specific lecture
open lecture-01/index.html
```

### Running Jupyter Notebooks

Some lectures include interactive Jupyter notebooks for live demos. To run them:

1. Install [uv](https://docs.astral.sh/uv/) (Python package manager):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

2. Install dependencies and start JupyterLab:
```bash
uv sync
uv run jupyter lab
```

3. Open the notebook (e.g., `lecture-01/tokenize.ipynb`) in JupyterLab.

4. To view as slides, use the RISE extension (enter slideshow mode from the toolbar).

### Exporting RISE Slides to HTML

To convert a Jupyter notebook to standalone HTML slides:

```bash
jupyter nbconvert --to slides --embed-images lecture-01/tokenize.ipynb
```

Then add the UChicago theme by inserting this line right before `</head>` in the generated HTML file:

```html
<link href="../assets/css/uchicago-theme.css" rel="stylesheet"/>
```

## Deploying to GitHub Pages

1. Push your repository to GitHub

2. Enable GitHub Pages:
   - Go to your repository settings
   - Navigate to "Pages" in the left sidebar
   - Under "Source", select "main" branch
   - Click "Save"

3. Your slides will be available at `https://uchicago-nlp-course.github.io/winter2025-lectures/`

## Navigation Controls

When viewing slides:
- **Arrow keys** or **click**: Navigate through slides
- **Spacebar**: Next slide
- **Esc** or **O**: Overview mode
- **F**: Fullscreen modec
- **?**: Help

## Reveal.js Features Used

- Slide transitions
- Syntax highlighting for code
- Speaker notes
- Overview mode
- Mobile-friendly responsive design

## Customization

### Adding Custom Styles

Add custom CSS in the `<style>` section of each lecture's HTML file, or create a shared CSS file in `assets/css/`.

### Adding Images

Place images in `assets/images/` and reference them in your slides:
```html
<img src="../assets/images/example.png" alt="Description">
```

### Creating New Lectures

1. Copy the template from an existing lecture
2. Update the title and content
3. Add a link to the new lecture in `index.html`

## License

Course materials © 2025 Chenhao Tan, University of Chicago.

## Credits

Slides created using [reveal.js](https://revealjs.com/).
