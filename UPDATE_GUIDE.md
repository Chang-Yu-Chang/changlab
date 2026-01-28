## Quick Update Guide

### Add a Team Member

Edit `_data/people.yml` and add:

```yaml
- name: "First Last"
  name_zh: "Chinese Name"
  role: "Position Title"
  pronouns: "he/him"
  image: "images/people_firstname.jpg"
  bio: "Bio text here"
  outside_science: "Optional personal interests"
  email: "email@sinica.edu.tw"
  links:
    - label: "GitHub"
      url: "https://github.com/username"
    - label: "CV"
      url: "files/cv.pdf"
```

### Add a Publication

Edit `_data/publications.yml` and add:

```yaml
- id: 9
  title: "Paper Title"
  authors: "<u>Your Name</u>, Co-Author Name"
  journal: "Journal Name"
  year: 2026
  volume: 10
  issue: "2"
  pages: "123–145"
  url: "https://doi.org/..."
  threads:
    - url: "https://x.com/..."
      label: "X thread"
  notes:
    - url: "https://..."
      label: "Coverage"
```

### Remove Old Image Folders

```bash
cd images
rmdir people/
rmdir index/
rmdir index/deprecated/
rmdir research/  # if empty
```

**That's it!** Pages regenerate automatically when you rebuild the site.
