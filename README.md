# robynpan.github.io

Single-page site. The page never reloads — clicking a card swaps the hero panel in place.

## Folder structure

```
robynpan.github.io/
├── index.html
├── about.html
└── projects/
    ├── projects.json          ← list of project folder names
    ├── smartwatch/
    │   ├── README.md          ← title, tags, body text
    │   └── images/
    │       ├── images.json    ← list of image filenames
    │       ├── 01.jpg
    │       └── 02.jpg
    └── solarpunk-jewels/
        ├── README.md
        └── images/
            ├── images.json
            └── 01.jpg
```

## Adding a new project

1. Create `projects/your-project-name/`
2. Write `README.md` in this format:

```markdown
# Your Project Title

tags: Tag One, Tag Two, Tag Three

Body text in normal markdown from here down.

## Subheadings work

- Lists work too
```

3. Add images to `projects/your-project-name/images/` and create `images.json`:

```json
["01.jpg", "02.jpg", "03.jpg"]
```

4. Add the folder name to `projects/projects.json`:

```json
["smartwatch", "solarpunk-jewels", "your-project-name"]
```

Reload the site — done.

## Shareable URLs

Each project gets a hash URL automatically:
- `robynpan.github.io/#smartwatch`
- `robynpan.github.io/#solarpunk-jewels`

Browser back/forward works correctly.
