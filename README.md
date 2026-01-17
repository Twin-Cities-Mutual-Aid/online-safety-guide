# Online Safety Guide

**Privacy-conscious access to existing resources, filling gaps where they exist.**

## Why This Exists

Excellent digital security guides already exist - [EFF Surveillance Self-Defense](https://ssd.eff.org/), [Activist Checklist](https://activistchecklist.org/), [Privacy Guides](https://www.privacyguides.org/). We're not trying to replace them.

But we noticed some gaps:

1. **Safe access** - How do you safely translate a security guide if you don't read English? Using Chrome's built-in translate sends your browsing to Google. Most guides don't cover this.

2. **Local resources** - Minnesota rapid response numbers, legal aid contacts, and mutual aid organizations are scattered across dozens of websites.

3. **Bridge content** - Digital security guides (EFF) and immigration resources (ILCM) exist separately. Nobody explicitly connects them for people facing both concerns.

4. **Language gaps** - EFF supports 12 languages but not Somali or Hmong - languages spoken by large Minnesota communities.

## What We Do

- **Original content where gaps exist** - Like our guide on safely translating web content
- **Minnesota-specific contacts** - Rapid response, legal aid, mutual aid in one maintained place
- **Annotated links** - Point to the best existing resources with context on what each covers
- **Translation support** - For languages underserved by existing guides

## What We Don't Do

- Rewrite comprehensive guides that EFF maintains better
- Compete with Activist Checklist's situation-based UX
- Collect any user data (no analytics, no cookies)
- Provide legal advice (we link to legal resources)

## The Honest Question

Before adding anything, we ask: *"Does this already exist somewhere trustworthy?"*

If yes → we link to it.
If no → we might have found a genuine gap worth filling.

---

## Proposed Site Structure

```
/
├── index.md                    # "What do you need help with?" → links out
├── guides/
│   ├── safe-translation.md     # ORIGINAL: how to safely translate content
│   ├── getting-started.md      # Which browser, basic setup, then links to EFF
│   └── digital-safety-immigrants.md  # Bridge: digital security + immigration
├── minnesota/
│   ├── emergency-contacts.md   # Rapid response, legal aid numbers
│   └── organizations.md        # Local orgs, mutual aid
├── resources/
│   └── external-guides.md      # Annotated links to EFF, Activist Checklist, etc.
│
├── /es/                        # Spanish translations
│   └── (mirrors structure above for translated content)
├── /so/                        # Somali translations
└── /hmn/                       # Hmong translations
```

### Translation Approach

- **Not translating everything** - Focus on original content we create (safe translation guide, MN contacts)
- **Don't duplicate EFF's work** - They already have 12 language translations for their guides
- **Community-reviewed** - Partner with local orgs for accurate translations, not machine translation
- **Searchable in-language** - Keywords in each language so people can search in Somali/Hmong and find relevant content

### Landing Page

Situation-based navigation that mostly links out:

| Situation | We Provide | Links To |
|-----------|------------|----------|
| Attending a protest | MN rapid response contacts | EFF, Activist Checklist |
| Securing my phone | "Start here" basics | EFF phone guides |
| Can't read English well | Safe translation guide | Firefox, Proton Lumo |
| Worried about ICE | MN contacts + bridge guide | ILCM, EFF |

---

## Proposed Technology

| Component | Choice | Why |
|-----------|--------|-----|
| Hosting | GitHub Pages | Free, transparent, no server to maintain |
| Generator | Jekyll | Simple, GitHub Pages native support |
| Search | [Pagefind](https://pagefind.app/) | Client-side, no tracking, fast |
| Analytics | None | Privacy-first - we don't track visitors |
| Styling | Minimal CSS | Fast loading, accessible, easy to maintain |

### Why These Choices

**GitHub Pages** - Free hosting, version-controlled content, easy for contributors to submit PRs.

**No analytics** - If we're telling people how to protect their privacy, we shouldn't be tracking them. We won't know our traffic numbers, and that's okay.

**Client-side search** - Pagefind builds a search index at deploy time. Search happens in the browser - no queries sent to a server.

---

## Status

This project is figuring out its scope. See [Issue #7](https://github.com/Twin-Cities-Mutual-Aid/online-safety-guide/issues/7) for the discussion.

## Questions / Feedback

Open an issue or comment on #7. We're figuring this out together.
