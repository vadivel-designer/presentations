# Claude Code Training Slides

Interactive Reveal.js presentation for Claude Code training at Kissflow.

## Quick Start

### Option 1: Open Directly
Simply open `index.html` in a modern browser (Chrome, Firefox, Safari, Edge).

### Option 2: Local Server (Recommended)
For the best experience, serve the files locally:

```bash
# Using Python 3
cd claude-code-slides
python -m http.server 8000

# Then open http://localhost:8000
```

Or use any static file server (Live Server in VS Code, etc.)

## Presenter Controls

| Key | Action |
|-----|--------|
| `S` | Open speaker notes view (IMPORTANT!) |
| `→` or `Space` | Next slide |
| `←` | Previous slide |
| `Esc` or `O` | Overview mode |
| `F` | Fullscreen |
| `B` | Blackout screen |
| `?` | Show all shortcuts |

## Speaker Notes

**Press `S` to open speaker view** - this shows:
- Current slide
- Next slide preview
- Speaker notes
- Timer

The speaker notes contain detailed talking points for each slide.

## Customization

### Update Branding
Edit `css/custom.css` to change:
- `--primary` - Main accent color
- `--secondary` - Secondary color
- `--accent` - Highlight color

### Add Your Demo Projects
Update slides 4-6 in `index.html` to reference your actual demo projects.

## Print to PDF

1. Open the presentation in Chrome
2. Add `?print-pdf` to the URL: `index.html?print-pdf`
3. Use Chrome's print dialog (Ctrl/Cmd + P)
4. Save as PDF

## Structure

```
claude-code-slides/
├── index.html      # Main presentation (58 slides)
├── css/
│   └── custom.css  # Custom styling
├── images/
│   ├── diagrams/   # Add flow diagrams here
│   └── screenshots/# Add terminal screenshots here
└── README.md       # This file
```

## Duration Guide

| Part | Slides | Duration |
|------|--------|----------|
| Part 1: Opening & Showcase | 1-8 | 15-20 min |
| Part 2: Must Know | 9-33 | 50 min |
| Part 3: Intermediate | 34-50 | 32 min |
| Part 4: Advanced | 51-53 | 5-10 min |
| Part 5: Closing | 54-58 | 5-10 min |
| **Total** | **58** | **~2 hours** |

## Pre-Training Checklist

- [ ] Test all demos before the session
- [ ] Open speaker view (`S` key) on presenter screen
- [ ] Have sample project ready for demos
- [ ] Test internet connection (for CDN resources)
- [ ] Have backup screenshots in case demos fail

## Resources

- [Reveal.js Documentation](https://revealjs.com/)
- [Claude Code Documentation](https://claude.ai/code)
- [Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)
