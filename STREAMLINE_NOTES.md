# Lab Website Streamlining - Setup Instructions

## ✅ Completed

### 1. Data Files Created
- **`_data/people.yml`** - Central repository for team member information with fields for:
  - Name, name (Chinese), role, pronouns
  - Profile image, bio, outside interests, email
  - Links (CV, GitHub, Google Scholar, etc.)
  
- **`_data/publications.yml`** - Central repository for publication records with fields for:
  - ID, title, authors, journal, year, volume, pages
  - Publication URL
  - Social media threads and additional notes

### 2. Image Renaming (Flat Structure)
Images renamed from nested folders to flat naming for easier management:
- `images/people/changyu.jpg` → `images/people_changyu.jpg`
- `images/people/tzuhsin.jpg` → `images/people_tzuhsin.jpg`
- `images/people/kuanfen.jpg` → `images/people_kuanfen.jpg`
- `images/people/luna.jpg` → `images/people_luna.jpg`
- `images/index/logo.png` → `images/index_logo.png`
- `images/index/as.jpg` → `images/index_as.jpg`
- `images/index/greenhouse1.jpg` → `images/index_greenhouse1.jpg`
- `images/index/greenhouse2.jpg` → `images/index_greenhouse2.jpg`

### 3. Updated File References
- `index.qmd` - Updated all image paths to flat naming
- `_quarto.yml` - Updated favicon path

### 4. Template Files Created
- **`people-template.qmd`** - Data-driven template that loops through `_data/people.yml`
- **`publications-template.qmd`** - Data-driven template that loops through `_data/publications.yml`

## ⚠️ Next Steps (Manual)

### Replace Current Files
Copy the content from the template files to replace the current versions:
1. Replace `people.qmd` with content from `people-template.qmd`
2. Replace `publications.qmd` with content from `publications-template.qmd`

### Remove Empty Folders
```bash
cd images
rmdir people/  # After confirming images moved
rmdir index/deprecated/  # If still empty
rmdir index/
rmdir research/  # If empty
```

## 💡 Future Updates

### Adding a New Team Member
Just add an entry to `_data/people.yml`:
```yaml
- name: "New Member"
  name_zh: "新成員"
  role: "Position"
  pronouns: "pronouns"
  image: "images/people_newmember.jpg"
  bio: "..."
  outside_science: ""
  email: "email@sinica.edu.tw"
  links:
    - label: "GitHub"
      url: "https://github.com/..."
```

### Adding a Publication
Just add to `_data/publications.yml`:
```yaml
- id: 9
  title: "New Research Title"
  authors: "..."
  journal: "Journal Name"
  year: 2026
  url: "https://..."
  threads: []
  notes: []
```

The pages will auto-generate!

## 📂 New Structure

```
changlab/
├── _data/
│   ├── people.yml          ← Team data (single source of truth)
│   └── publications.yml     ← Publication data (single source of truth)
├── images/
│   ├── people_*.jpg        ← Flat structure
│   ├── index_*.jpg         ← Flat structure
│   ├── icons/              ← Keep as-is
│   └── research/           ← Keep as-is
├── people.qmd              ← Loads _data/people.yml
├── publications.qmd        ← Loads _data/publications.yml
├── index.qmd               ← Updated image paths
└── _quarto.yml             ← Updated favicon path
```

## 🎯 Benefits

- **Reduced duplication**: Team info and pubs in one place
- **Faster updates**: Edit YAML, page auto-generates
- **Consistent formatting**: Template-driven layout
- **Easier maintenance**: Simpler file structure
- **Scalable**: Just add entries to YAML files
