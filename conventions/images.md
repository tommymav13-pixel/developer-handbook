# Images

This document describes the conventions for using images in project
documentation.

Images should support the documentation, not replace it.

---

# Purpose

Images are useful for:

- Screenshots
- Diagrams
- Architecture overviews
- Workflow illustrations
- Charts
- Project demonstrations

---

# Image Directory

Store images in a dedicated directory.

```text
images/
```

Example:

```text
project/
│
├── README.md
├── images/
│   ├── repository_structure.png
│   ├── git_workflow.png
│   └── portfolio_homepage.png
```

---

# Naming Convention

Use descriptive lowercase names.

Prefer **snake_case**.

Examples:

```text
repository_structure.png
git_workflow.png
portfolio_homepage.png
python_output_example.png
```

Avoid:

```text
Image1.png
Screenshot.png
New Image.png
```

---

# Supported Formats

Preferred:

- PNG
- SVG

Acceptable:

- JPG
- JPEG
- GIF (when animation is required)

Avoid:

- BMP
- TIFF

---

# Markdown Syntax

Basic syntax:

```markdown
![Repository Structure](images/repository_structure.png)
```

Relative path example:

```markdown
![Git Workflow](../images/git_workflow.png)
```

---

# Alternative Text

Always provide meaningful alternative text.

Good:

```markdown
![Git branch workflow diagram](images/git_workflow.png)
```

Poor:

```markdown
![Image](images/git_workflow.png)
```

Alternative text should describe the image.

---

# Image Size

Prefer reasonably sized images.

Avoid:

- Very large screenshots
- Blurry images
- Excessively compressed images

Crop unnecessary content before adding screenshots.

---

# Screenshots

Before uploading screenshots:

- Remove sensitive information.
- Crop unnecessary borders.
- Use high resolution.
- Keep the interface readable.

---

# Diagrams

When possible:

- Keep diagrams simple.
- Use consistent terminology.
- Label important components.
- Avoid unnecessary decoration.

---

# Current Convention

I use images to:

- Explain workflows
- Document project structure
- Demonstrate project output
- Improve technical documentation

Images should complement the written documentation rather than replace it.