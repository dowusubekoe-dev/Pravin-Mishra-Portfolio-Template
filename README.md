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

## Implementation Logic using JavaScript

For the implementation of the dynamic date in the footer, I choose option A

Option A (Beginner-friendly JS):

- Add a <span id="deployDate"></span> in footer where date goes
- Add JS that sets today’s date in DD Mon YYYY format

I used the toLocaleDateString method with the 'en-GB' locale to ensure the date follows the day-month-year convention. By targeting the deployDate ID, the script ensures the footer is always accurate to the user's local time without requiring manual HTML updates during the deployment process.


```js
<script>
  function formatDeployDate() {
    const date = new Date();
    
    // Options to get the "DD Mon YYYY" format
    const options = { day: '2-digit', month: 'short', year: 'numeric' };
    
    // Formats date to: "04 Feb 2026"
    const formattedDate = date.toLocaleDateString('en-GB', options);
    
    // Inject into the HTML element
    document.getElementById('deployDate').textContent = formattedDate;
  }

  // Run the function when the page loads
  window.onload = formatDeployDate;
</script>

```

✅ This proof must be visible in your browser screenshot submission.