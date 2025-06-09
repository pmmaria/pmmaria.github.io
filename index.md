---
layout: default
title: "Home"
---

<div style="text-align: center; margin-bottom: 2rem;">
  <img src="assets/profile.jpg" alt="Maria de los Angeles Perez" width="150" style="border-radius: 50%;">
  <h1>Maria de los Angeles Perez</h1>
  <h3>Data Analyst • Project Explorer</h3>
  <p>
    <a href="https://github.com/pmmaria" target="_blank">GitHub</a> |
    <a href="https://www.linkedin.com/in/maria-perez1205" target="_blank">LinkedIn</a> |
    <a href="mailto:mary.perez.m@gmail.com">Email</a>
  </p>
</div>

# 👋 Welcome

## Hi, I’m Maria

I’m a data analyst originally from Santiago, Chile — now based in Copenhagen, Denmark.

I work with data to find patterns, solve problems, and make things clearer. I have experience in industries like mining, logistics, and retail — mostly using SQL, Python, and BI tools to support better decisions.

This site is where I keep track of what I’m learning and share some of the projects I’ve been working on. It’s a mix of real-world data, experiments, and things I find interesting

---

## 🔍 Current Project: Inside Airbnb – Santiago

Right now, I'm diving into Airbnb data for Santiago — my hometown — using datasets from [Inside Airbnb](http://insideairbnb.com/get-the-data.html). Knowing the city well gives me an edge in exploring trends around:

- 📅 Availability patterns  
- 💰 Pricing and listing characteristics  
- 💬 Guest feedback and review activity  

All analysis is done in Jupyter notebooks and summarized in blog posts.

➡️ [Read the first post](2025/06/08/exploring-airbnb-santiago-chile.html)  
➡️ [View the GitHub repo](https://github.com/pmmaria/inside_airbnb)

---

## 🛠️ Tools I Use

- Python (Pandas, NumPy, Matplotlib)
- Jupyter Notebooks
- `uv` for environment and dependency management
- Google Cloud for file storage
- VSCode
- Python + pandas + Jupyter Notebooks
- GitHub Pages + Jekyll for this site
- Looker Studio
  
---

## 🧭 What’s Next?

I’ll continue adding new projects — from BI dashboards to data pipelines and machine learning experiments. Each one reflects something I'm learning, experimenting with, or simply curious about.

---

## 👩‍💻 About This Site

This blog is a personal space to reflect on my journey through data.  
I write about what I’m building, learning, or testing. My goal is to improve, stay curious, and connect with others in the field.

If you find something interesting or want to chat, feel free to reach out.

📫 mary.perez.m@gmail.com  
💼 [LinkedIn](https://www.linkedin.com/in/maria-perez1205)  
🐙 [GitHub](https://github.com/pmmaria)

---

## 📚 Blog Posts

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> – {{ post.date | date: "%Y-%m-%d" }}</li>
  {% endfor %}
</ul>

