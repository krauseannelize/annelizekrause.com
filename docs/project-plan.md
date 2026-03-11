# Project Plan: annelizekrause.com

## 1. Project Overview

A professional portfolio website to showcase skills, projects, and personal brand to recruiters, hiring managers, and potential clients. The site serves as a centralized, self-owned platform, independent of any single social media service, providing full control over content, branding, and online presence. Designed to be accessible to non-technical audiences who make hiring decisions.

## 2. Goals & Success Criteria

### Goals

1. Establish a professional online presence beyond LinkedIn.
2. Provide recruiters and hiring managers with a shareable link to my work.
3. Showcase projects that demonstrate my skills in a way non-technical people can understand.
4. Make it easy for potential employers or clients to contact me.

### Success Criteria

- [x] Site is live at [annelizekrause.com](https://annelizekrause.com) with HTTPS  
- [ ] `Home`, `About`, `Portfolio`, and `Contact` sections are functional  
- [ ] At least one project is showcased with a description and visuals  
- [ ] Contact form works and delivers messages to email  
- [ ] Site is mobile-friendly and loads in under 3 seconds  
- [ ] A recruiter can share the link with a client and it looks professional  

## 3. Scope

- `Home` section with name, tagline, and introduction
- `About` section with professional story and skills
- `Portfolio` section with project cards (images and descriptions)
- `Contact` section with a contact form (FormSpree)
- Mobile-responsive design
- Hosted on GitHub Pages with custom domain
- Branding: use existing color palette, fonts and logo used for LinkedIn engagement

## 4. Requirements

### Functional: What the site does

- Site acts as an in-depth resume, putting a face and personality to the work
- Soft skills are as visible as technical skills throughout the content
- Contact form sends submissions directly to Gmail
- All professional contact points listed (LinkedIn, email, etc.)
- Portfolio projects presented with visuals and descriptions accessible to non-technical audiences

### Non-functional: How well the site does it

- Responsive design across all devices (desktop, tablet, mobile)
- Accessible design following EU accessibility standards, including colorblind-friendly color choices
- Cross-browser compatibility (Chrome, Firefox, Safari, Edge)
- Page load under 3 seconds

## 5. Tech Stack

| Component | Choice | Why |
|-----------|--------|-----|
| Static site generator | Hugo | Fast builds, markdown content, no server needed |
| Theme | Hugo Profile | Pre-built portfolio sections, contact form, blog, easy config |
| Hosting | GitHub Pages | Free, reliable, integrates with repo |
| CI/CD | GitHub Actions | Auto-deploys on push to main |
| Domain registrar | Namecheap | annelizekrause.com |
| Contact form | FormSpree | Free tier, no backend needed, built into theme |
| Fonts | Barlow Bold (headings), TBD web-safe body font | Consistent branding across site and LinkedIn content |
| Version control | Git/GitHub | Public repo |

## 6. Site Structure

### Home

- Professional headshot, name, and tagline
- Brief elevator pitch (who I am, what I do, why it matters)
- CTA buttons ("View my work", "Get in touch")

### About

- Personal story: where I come from, what motivates me, what I love
- Candid photos (personality, not just professional)
- Skills and tools summary

### Portfolio

- Project cards with: title, description, image/screenshot, tags (tech used)
- Each tag represents a skill or tool (e.g. Power BI, Excel, Python, SQL)
- Tags will act as filters once there are enough projects to make filtering useful
- Start with basic cards; interactive filtering is a future enhancement

### Contact

- Contact form (FormSpree) for quick, low-friction messages
- Links to all relevant profiles: GitHub, LinkedIn, email
- Central hub so visitors can reach out however they prefer

---

## Feature Creep

A running list of ideas, improvements, and nice-to-haves. Nothing here is a priority. Items move into scope only when the current version is shipped.

- SEO optimization
- Short-form logo/icon for favicon and compact branding
- Educational section with resources
- Dedicated business email
- Client billing and invoicing
- Login and authentication
- Blog section with regular content
- E-commerce or payment processing
