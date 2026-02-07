# 🚀 Quick Start Guide

## Create New Post
```bash
hugo new posts/[topic]/[title].md
```

## Preview Site
```bash
hugo server -D
```
Visit: http://localhost:1313/my-blog/

## Publish
```bash
git add .
git commit -m "Your commit message"
git push
```

## Common Frontmatter Template
```yaml
---
title: "Your Post Title"
date: 2026-02-07
draft: false
topics: ["Topic1", "Topic2"]
tags: ["tag1", "tag2"]
categories: ["Category"]
description: "Brief description"
ShowToc: true
---
```

## For Private Posts
Add to frontmatter:
```yaml
private: true
```

## Add Images
1. Put in `static/images/`
2. Use: `![Alt](/images/name.jpg)`

## Add YouTube Video
```markdown
{{</* youtube VIDEO_ID */>}}
```

## Comments Setup
1. Enable Discussions in GitHub repo settings
2. Visit https://giscus.app/
3. Enter: chronic700/my-blog
4. Copy configuration values
5. Update `layouts/partials/comments.html`

## Google Analytics
Update `hugo.toml`:
```toml
googleAnalytics = "G-YOUR-ID"
```

## File Locations
- Posts: `content/posts/[topic]/`
- Images: `static/images/`
- Custom CSS: `assets/css/extended/custom.css`
- Configuration: `hugo.toml`

## Your Site
- Local: http://localhost:1313/my-blog/
- Live: https://chronic700.github.io/my-blog/

## Full Guides
- **Content Creation**: See `CONTENT-GUIDE.md`
- **Setup & Deployment**: See `SETUP-GUIDE.md`

---

**Need Help?** Check the full guides or Hugo documentation at https://gohugo.io/
