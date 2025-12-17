# Writing Slides in Markdown

Reveal.js supports writing slides in Markdown, which is much easier than writing HTML!

## Three Options

### Option 1: Inline Markdown (Easiest)

Write Markdown directly inside your HTML file. See `lecture-02/index.html` for a complete example.

```html
<section data-markdown>
    <textarea data-template>
        ## Slide Title
        - Bullet point 1
        - Bullet point 2

        Note: These are speaker notes
    </textarea>
</section>
```

**Pros:**
- Everything in one file
- Easy to get started
- Can mix with HTML slides

**Cons:**
- Can get messy with lots of content
- HTML escaping can be tricky

### Option 2: External Markdown File (Recommended)

Write your slides in a separate `.md` file. See `lecture-03/slides.md` and `lecture-03/index.html` for a complete example.

**slides.md:**
```markdown
# Title Slide

---

## Second Slide

Content here...

---

## Third Slide

- Point 1
- Point 2
```

**index.html:**
```html
<section data-markdown="slides.md"
         data-separator="^\n---\n$"
         data-separator-vertical="^\n--\n$">
</section>
```

**Pros:**
- Clean separation of content and presentation
- Easy to edit in any Markdown editor
- Version control friendly

**Cons:**
- Need to run a local server for development (see below)

### Option 3: Pure HTML

Write traditional HTML slides. See `lecture-01/index.html` for an example.

**Pros:**
- Full control over layout
- Can use complex HTML/CSS

**Cons:**
- More verbose
- Harder to edit quickly

## Markdown Syntax

### Slide Separators

- **Horizontal slides** (left/right): Use `---`
- **Vertical slides** (up/down): Use `--`

```markdown
# Slide 1

---

# Slide 2

--

## Subsection of Slide 2

---

# Slide 3
```

### Text Formatting

```markdown
## Headers use ##

**Bold text**
*Italic text*
`code inline`

- Bullet lists
- Use dashes

1. Numbered lists
2. Use numbers
```

### Code Blocks

Use triple backticks with language name:

````markdown
```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)
```
````

### Images

```markdown
![Alt text](../assets/images/example.png)
```

### Links

```markdown
[Link text](https://example.com)
```

### Speaker Notes

```markdown
## Slide Title

Visible content here.

Note:
These are speaker notes. Press 'S' to see them.
```

### Fragments (Progressive Display)

```markdown
- Item 1 <!-- .element: class="fragment" -->
- Item 2 <!-- .element: class="fragment" -->
- Item 3 <!-- .element: class="fragment" -->
```

### Two-Column Layout

You can embed HTML in Markdown:

```markdown
## Two Columns

<div style="display: flex;">
<div style="flex: 1;">

Left column content
- Bullet 1
- Bullet 2

</div>
<div style="flex: 1;">

Right column content
- Bullet A
- Bullet B

</div>
</div>
```

## Local Development with External Markdown

External Markdown files require a local web server due to browser security restrictions.

### Option 1: Python

```bash
# Python 3
python -m http.server 8000

# Then open: http://localhost:8000
```

### Option 2: Node.js

```bash
npx http-server -p 8000
```

### Option 3: VS Code

Install the "Live Server" extension and click "Go Live" in the status bar.

## Mixing Markdown and HTML

You can mix both in the same presentation:

```html
<div class="slides">
    <!-- Markdown slide -->
    <section data-markdown>
        <textarea data-template>
            ## Markdown Slide
            Easy to write!
        </textarea>
    </section>

    <!-- HTML slide -->
    <section>
        <h2>HTML Slide</h2>
        <p>Full control!</p>
    </section>
</div>
```

## Best Practices

1. **Start with external Markdown** for quick content creation
2. **Use HTML** when you need precise layout control
3. **Keep slides simple** - less text is better
4. **Use code highlighting** for technical content
5. **Add speaker notes** to remember what to say
6. **Test on different screen sizes** - slides should be readable

## Complete Example

**lecture-04/slides.md:**
```markdown
# CMSC 25700/35100
## Natural Language Processing

### Lecture 4: Language Modeling

**Chenhao Tan**

---

## What is Language Modeling?

Predicting the next word in a sequence

--

### Example

"The cat sat on the ___"

Likely words: mat, floor, chair
Unlikely words: sky, telescope

---

## N-gram Models

```python
# Bigram model
P(w_i | w_{i-1})

# Trigram model
P(w_i | w_{i-2}, w_{i-1})
```

Note:
Explain that n-grams look at context windows

---

## Questions?
```

## Resources

- [Reveal.js Markdown Documentation](https://revealjs.com/markdown/)
- [Markdown Guide](https://www.markdownguide.org/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)
