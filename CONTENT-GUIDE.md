# 📝 Blog Content Creation Guide

## Quick Start: Creating a New Post

### Using Hugo Command (Easiest)
```bash
hugo new posts/your-topic/your-post-title.md
```

This creates a new post with the correct frontmatter template.

### Manual Creation
Create a file in `content/posts/[topic-name]/your-post.md`

## 📋 Post Template

```markdown
---
title: "Your Amazing Post Title"
date: 2026-02-07
draft: false  # Set to true to keep it unpublished
private: false  # Set to true for private posts
topics: ["Technology", "Innovation"]
tags: ["ai", "future", "ideas"]
categories: ["Technology"]
description: "A compelling summary of your post"
cover:
    image: "images/cover.jpg"  # Optional cover image
    alt: "Cover image description"
    caption: "Image caption"
ShowToc: true  # Show table of contents
TocOpen: true  # Open TOC by default
---

## Your Content Here

Write your amazing ideas!
```

## 🎨 Adding Media

### Images
```markdown
![Alt text](../../images/your-image.jpg)

Or with HTML for more control:
<img src="../../images/your-image.jpg" alt="Description" width="600px">
```

**Image Organization:**
- Put images in `static/images/[topic]/`
- Reference them as `/images/[topic]/image.jpg` in posts

### Videos

#### YouTube
```markdown
{{</* youtube VIDEO_ID */>}}
```

#### Local Videos
```html
<video width="100%" controls>
  <source src="/videos/your-video.mp4" type="video/mp4">
</video>
```

### GIFs
```markdown
![Cool Animation](/images/animation.gif)
```

### Embedding Other Content

#### Twitter/X
```html
<blockquote class="twitter-tweet">
  <a href="TWEET_URL"></a>
</blockquote>
<script async src="https://platform.twitter.com/widgets.js"></script>
```

#### CodePen
```html
<iframe height="500" src="https://codepen.io/USERNAME/embed/PEN_ID" frameborder="0"></iframe>
```

## 📁 Content Organization

### Folder Structure
```
content/
├── posts/
│   ├── technology/
│   │   ├── ai-post.md
│   │   └── web3-post.md
│   ├── philosophy/
│   │   └── thinking-post.md
│   ├── design/
│   │   └── ux-post.md
│   └── personal/  # For private posts
│       └── private-thoughts.md
```

### Topics Taxonomy
Use the `topics` field to organize content:
- Technology
- Philosophy
- Design
- Business
- Personal
- Science
- Art

You can create new topics as needed!

## 🔒 Creating Private Posts

### Method 1: Simple Hiding (from listings)
Add `private: true` to frontmatter. Post won't appear in listings but URL is still accessible.

### Method 2: Password Protection (Recommended)
1. Add `private: true` to frontmatter
2. Set `layout: "private"` in frontmatter
3. The password page will show automatically

### Method 3: Draft Mode (for work-in-progress)
Add `draft: true` to frontmatter. Won't be published at all.

## ✍️ Writing Tips

### Code Blocks
\`\`\`python
def hello_world():
    print("Hello, World!")
\`\`\`

### Callouts/Alerts
```markdown
> **Note:** This is important information

> **Warning:** Be careful here

> **Tip:** Pro tip for readers
```

### Math Equations (if needed)
```markdown
Inline: $E = mc^2$

Block:
$$
\frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$
```

### Tables
```markdown
| Feature | Status |
|---------|--------|
| Images  | ✅     |
| Videos  | ✅     |
| Comments| ✅     |
```

## 🚀 Publishing Workflow

### 1. Create Content
```bash
hugo new posts/technology/my-new-post.md
```

### 2. Edit Content
Open the file and write your content

### 3. Preview Locally
```bash
hugo server -D
```
Visit http://localhost:1313/my-blog/

### 4. Publish
```bash
git add .
git commit -m "Add new post: [post title]"
git push
```

GitHub Actions will automatically build and deploy!

## 🎨 Customization

### Adding Custom CSS
Create `assets/css/extended/custom.css`:
```css
/* Your custom styles */
.special-section {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    padding: 2rem;
    border-radius: 8px;
    color: white;
}
```

### Custom Shortcodes
Create custom shortcodes in `layouts/shortcodes/`:

Example: `layouts/shortcodes/alert.html`
```html
<div class="alert alert-{{ .Get 0 }}">
    {{ .Inner }}
</div>
```

Usage in posts:
```markdown
{{</* alert "info" */>}}
This is an informational message
{{</* /alert */>}}
```

## 📊 Google Analytics

Update your GA ID in `hugo.toml`:
```toml
[params]
  googleAnalytics = "G-XXXXXXXXXX"
```

## 💬 Comments Setup

### Enable Giscus Comments
1. Go to https://giscus.app/
2. Enter your repo: `chronic700/my-blog`
3. Enable Discussions in your GitHub repo settings
4. Copy the generated code values
5. Update `layouts/partials/comments.html` with your values

### Moderating Comments
- All comments are GitHub Discussions
- Moderate them in your repo's Discussions tab
- You have full control: edit, delete, lock threads

## 🔍 SEO Optimization

Always include:
```yaml
description: "Compelling meta description (150-160 chars)"
tags: ["relevant", "keywords", "here"]
cover:
    image: "path/to/image.jpg"  # For social sharing
```

## 📱 Testing

### Local Testing
```bash
hugo server -D
```

### Build Testing
```bash
hugo --minify
```

Check the `public/` folder for generated site.

## 🆘 Troubleshooting

### Post not showing?
- Check `draft: false`
- Check `private: false` (unless intended)
- Ensure date is not in future

### Images not loading?
- Images should be in `static/` folder
- Reference them as `/images/name.jpg` (no 'static' in path)

### Styles look broken?
```bash
hugo server --disableFastRender
```

## 🎯 Best Practices

1. **Use descriptive filenames**: `ai-future-trends.md` not `post1.md`
2. **Organize by topic**: Use folders for different subjects
3. **Write good descriptions**: They appear in listings and search results
4. **Use topics and tags**: Helps readers find related content
5. **Add cover images**: Makes posts visually appealing
6. **Enable TOC for long posts**: `ShowToc: true`
7. **Preview before publishing**: Always test locally first

---

## 🌟 Quick Reference

| Task | Command |
|------|---------|
| New post | `hugo new posts/topic/title.md` |
| Preview | `hugo server -D` |
| Build | `hugo --minify` |
| Publish | `git add . && git commit -m "msg" && git push` |

Happy blogging! 🚀
