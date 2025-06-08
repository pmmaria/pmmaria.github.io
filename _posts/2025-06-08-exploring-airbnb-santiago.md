---
layout: post
title: "Exploring Airbnb Data for Santiago, Chile"
date: 2025-06-08
---

I started a small data project using real data from [Inside Airbnb](http://insideairbnb.com/), focusing on listings in Santiago, Chile. The idea is to explore the data, clean it, and look for interesting insights around prices, availability, and reviews.

This blog will help me document the process step-by-step, while also serving as part of my portfolio for future recruiters.

---

### 🔧 Project Setup

I downloaded several CSV files provided by Inside Airbnb and created a project to analyze them using:

- **Python** + **Jupyter notebooks**
- The `uv` package manager (from Astral) to manage my virtual environment
- **VSCode** as my main editor
- A **Google Cloud** project to store my cleaned datasets


Setting up the virtual environment with `uv` was really fast, and I like that it automatically keeps a lock file for reproducibility.

---

### 🗂️ Datasets

I’m working with five files:

- `calendar.csv.gz`
- `listings.csv` (a smaller subset)
- `listings.csv.gz` (the full version)
- `reviews.csv` (subset)
- `reviews.csv.gz` (full version)

In my first notebook (`01_exploratory_analysis.ipynb`), I loaded each of these files into a pandas DataFrame and printed basic information: shape, column names, data types, and sample rows.

This helped me understand what’s inside and decide which tables to focus on.

---

### 📌 First Observations

Some quick notes from the initial exploration:

- The **calendar** file contains daily availability and price data for each listing.
- The **full listings** file includes a lot of metadata, like host info, location, and room details.
- The **reviews** file has review comments and dates — might be useful to see how active listings are.

---

### 🧹 Next Steps

I’ve decided to work with these three tables:

- `calendar`  
- `listings.csv.gz` (full version)  
- `reviews.csv.gz` (full version)  

The next step is to start cleaning them: fix column names, handle missing values, and standardize price and date formats.

I’ll document everything as I go — stay tuned!

---

Thanks for reading! If you have questions or feedback, feel free to reach out or follow the project on [GitHub](#).

