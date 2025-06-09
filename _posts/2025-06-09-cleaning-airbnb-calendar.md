---
layout: post
title: "🗓️ Cleaning the Airbnb Calendar Data"
date: 2025-06-09
categories: [project]
---

In this post, I’m cleaning the `calendar` table from the Inside Airbnb dataset for Santiago. The goal is to prepare a clean version I can upload to Google Cloud — basically simulating an ETL process.

---

## 🧼 Step 1: Check What’s Going On

After loading the data, the first thing I noticed was that several columns had weird data types — like prices stored as text and dates as strings. Not great for analysis, so I did a quick inspection to figure out what needed to be fixed:

```python
for col in df_calendar.select_dtypes(include='object').columns:
    print(f"==> {col}")
    print(df_calendar[col].map(type).value_counts())
```

## 🔁 Step 2: Convert Columns to Proper Types

I converted columns to the right data types to make analysis easier:

- `date` → datetime  
- `price` → float (after cleaning `$` and `,` symbols)  
- `available` → boolean (mapping `'t'` and `'f'` to True/False)

Here’s how I did it:

```python
df_calendar['date'] = pd.to_datetime(df_calendar['date'], format='%Y-%m-%d')
df_calendar['price'] = df_calendar['price'].replace({r'\$': '', r',': ''}, regex=True).astype(float)
df_calendar['available]()_
```
I also added a new column with prices converted to USD (using an exchange rate of 0.0011) for easier interpretation.

## 📈 Step 3: Price Insights

I explored the price column to understand the range and spot any weird values.

```python
# Summary statistics for price
print(df_calendar['price'].describe())
print("99th percentile:", df_calendar['price'].quantile(0.99))
```
#### What I found:
 - Prices vary a lot — from 11 CLP up to 89 million CLP!
 - The average price is about 71,616 CLP but is skewed by extreme values.
 - 99% of listings are below 450,000 CLP.
 - Most prices fall between 25,000 and 56,000 CLP.
 - Some very low prices like 11 CLP seem unrealistic.

Next, I decided to visualize the distribution to get a better sense of it.

## 📊 Step 4: Understand the Price Distribution

The price column had some crazy outliers — from 11 CLP up to 89 million CLP! That was inflating the average, so I plotted a histogram with a log scale to see the real distribution better.

```python
import matplotlib.pyplot as plt

reasonable_prices = df_calendar[df_calendar['price'] < 450000]['price']

plt.figure(figsize=(10, 6))
plt.hist(reasonable_prices, bins=50)
plt.title("Distribution of Airbnb Prices in CLP (Under 450,000)")
plt.xlabel("Price (CLP)")
plt.ylabel("Number of Listings")
plt.yscale('log')
plt.show()
```

Here’s the histogram:

![Price Distribution Histogram](/assets/price_distribution_u450.png)

Most prices were under 100,000 CLP per night. I decided to keep listings with prices under 450,000 CLP, which covers 99% of the data, and remove extreme low and high values for now.

## 🧹 Step 5: Final Cleaning and Save

- I renamed some columns for clarity and dropped unused ones
- I filtered the data to keep prices between 7,000 and 450,000 CLP.
- To make prices easier to understand for everyone (not just Chileans), I added a price_usd column.

*** Now it’s ready to upload to Google Cloud for further analysis. 🎉***

### 🔍 What I Learned

- Always inspect column types — especially object columns.
- Use log scales when visualizing skewed data.
- Adding columns like USD price improves clarity.
- Keep transformations simple and well-documented — just like a mini ETL.

- Next step: cleaning the reviews table.

➡️ [Back to project overview](#)  
➡️ [GitHub repo](https://github.com/pmmaria/inside_airbnb)

Thanks for reading!
— Maria



