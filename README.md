# annelizekrause.com

Personal portfolio and professional website for Annelize Krause.

**Live site:** [annelizekrause.com](https://annelizekrause.com)

## Tech Stack

- [Hugo](https://gohugo.io/) (static site generator)
- [Hugo Profile](https://github.com/gurusabarish/hugo-profile) theme
- Hosted on GitHub Pages

## Local Development

### Prerequisites

- [Hugo](https://gohugo.io/installation/) (extended edition)
- Git

### Setup

```bash
# Clone the repo with submodules
git clone --recurse-submodules https://github.com/krauseannelize/annelizekrause.com.git

# If already cloned without submodules
git submodule update --init --recursive
```

### Run locally

```bash
hugo server --buildDrafts
```

Site will be available at `http://localhost:1313`
