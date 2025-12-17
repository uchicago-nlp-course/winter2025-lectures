# Reveal.js Themes and Backgrounds

## Built-in Themes

Replace the theme CSS link in your HTML file:

```html
<!-- Default themes -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/white.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/league.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/beige.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/sky.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/night.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/serif.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/simple.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/solarized.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/moon.min.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/blood.min.css">
```

### Theme Previews

- **white** - Clean white background (current default)
- **black** - Black background, white text
- **league** - Gray background with cyan accents
- **beige** - Warm beige background
- **sky** - Blue gradient background
- **night** - Dark purple/black
- **serif** - Serif fonts, warm colors
- **simple** - Minimal, high contrast
- **solarized** - Popular Solarized color scheme
- **moon** - Dark blue theme
- **blood** - Dark with red accents

## Custom University of Chicago Theme

I've created a custom UChicago-themed style in `assets/css/uchicago-theme.css`.

### How to Use It

In your HTML `<head>` section:

```html
<!-- Replace the default theme with UChicago theme -->
<link rel="stylesheet" href="../assets/css/uchicago-theme.css">
```

**Features:**
- UChicago maroon (#800000) for headings
- Light gray background (#f5f5f5)
- Special classes: `.title-slide`, `.section-slide`
- Utility classes: `.maroon`, `.gold`, `.dark-gray`

## Per-Slide Background Options

### 1. Solid Color Background

```html
<section data-background-color="#800000">
    <h2 style="color: white;">Maroon Background</h2>
</section>
```

### 2. Gradient Background

```html
<section data-background-gradient="linear-gradient(45deg, #800000 0%, #a50000 100%)">
    <h2 style="color: white;">Gradient Background</h2>
</section>
```

### 3. Image Background

```html
<section data-background-image="../assets/images/chicago.jpg"
         data-background-size="cover"
         data-background-opacity="0.3">
    <h2>Image Background</h2>
</section>
```

**Image options:**
- `data-background-size`: `cover`, `contain`, or specific size
- `data-background-position`: `center`, `top left`, etc.
- `data-background-opacity`: `0.0` to `1.0`
- `data-background-repeat`: `repeat`, `no-repeat`

### 4. Video Background

```html
<section data-background-video="../assets/video/demo.mp4"
         data-background-video-loop
         data-background-video-muted>
    <h2>Video Background</h2>
</section>
```

### 5. IFrame Background

```html
<section data-background-iframe="https://example.com"
         data-background-interactive>
    <h2>Interactive Background</h2>
</section>
```

## Custom CSS Classes

Define custom backgrounds in your `<style>` section:

```html
<style>
    .reveal section.dark-slide {
        background-color: #2c3e50;
        color: white;
    }

    .reveal section.dark-slide h2 {
        color: #3498db;
    }
</style>
```

Then use the class:

```html
<section class="dark-slide">
    <h2>Custom Styled Slide</h2>
</section>
```

## Global Background Settings

Set a default background for all slides in the Reveal.initialize():

```javascript
Reveal.initialize({
    // ... other options

    // Default background color
    backgroundColor: '#f5f5f5',

    // Background transition
    backgroundTransition: 'fade', // or 'slide', 'convex', 'concave', 'zoom'
});
```

## Complete Example

See `lecture-04/index.html` for a working example showing all these methods.

## Quick Copy-Paste Examples

### Professional Dark Theme
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/black.min.css">
```

### Light and Clean
```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/reveal.js/4.5.0/theme/simple.min.css">
```

### UChicago Brand
```html
<link rel="stylesheet" href="../assets/css/uchicago-theme.css">
```

### Slide with Maroon Background
```html
<section data-background-color="#800000">
    <h2 style="color: white;">Content Here</h2>
</section>
```

### Slide with Subtle Image
```html
<section data-background-image="../assets/images/campus.jpg"
         data-background-opacity="0.2">
    <h2>Content is still readable</h2>
</section>
```
