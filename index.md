---
layout: default
title: "Home"
---

# 📝 Blog Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%Y-%m-%d" }}
    </li>
  {% endfor %}
</ul>


# 👋 Welcome!

Hi! I'm currently working on a data analysis project using real Airbnb data for **Santiago, Chile**.  
I'm using Python, Jupyter, and Google Cloud to explore listings, availability, prices, and reviews.

This site is where I share my process, code, and findings — step by step.

---

## 🔍 Current Project: Inside Airbnb – Santiago

I'm using data from [Inside Airbnb](http://insideairbnb.com/get-the-data.html) and focusing on:

- 📅 **Availability trends** (calendar data)
- 💰 **Price analysis** (listings)
- 💬 **Guest reviews** (reviews)

All my analysis is in notebooks, and each post summarizes what I’ve done and learned.

➡️ [Start reading here](2025/06/08/exploring-airbnb-santiago-chile.html)  
➡️ [See the GitHub repo](https://github.com/pmmaria/inside_airbnb)


---

## 🛠️ Tools I Use

- Python + pandas + Jupyter Notebooks
- `uv` for environment and dependency management
- Google Cloud for file storage
- VSCode
- GitHub Pages + Jekyll for this site

---

## 📬 About Me

I'm learning data analysis and building this blog to improve my skills and connect with recruiters.  
I like practical, real-world data, and documenting my learning journey.

If you're a recruiter or just curious, feel free to get in touch!

📫 Email: mary.perez.m@gmail.com  

💼 [LinkedIn](https://www.linkedin.com/in/maria-perez1205)

🐙 [GitHub](https://github.com/pmmaria)

