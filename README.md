# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:

```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
```

Add this line (example):

```html
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
```

✅ This proof must be visible in your browser screenshot submission.

## Deploy Date and Timestamp Display

This feature automatically displays the current date and timestamp on your deployment page. It dynamically updates whenever the page loads, showing when the deployment was last accessed or when the site was last deployed.

### Overview

The script formats the current date and time in a user-friendly format and injects it into a designated HTML element. This is useful for displaying deployment information, last update timestamps, or build dates on your website.

### Implementation

#### 1. Add the HTML Element

Place this in your HTML where you want the date and timestamp to appear:

```html
<p>Last Deployed: <span id="deployDate"></span></p>
```

#### 2. Add the JavaScript

Include this script in your HTML file (typically before the closing `</body>` tag or in a separate JS file):

```javascript
<script>
const options = { day: '2-digit', month: 'short', year: 'numeric' };
const timeOptions = { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: false };
const date = new Date();
const formattedDate = date.toLocaleDateString('en-GB', options).replace(',', '');
const formattedTime = date.toLocaleTimeString('en-GB', timeOptions);
document.getElementById('deployDate').textContent = `${formattedDate} ${formattedTime}`;
</script>
```

### Output Format

**24-Hour Format (Default):**
