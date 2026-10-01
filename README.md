

# 📊 Data Science Visualization Course

## Matplotlib + Seaborn — Practical EDA

### 🎯 Course Goal

Course complete karne ke baad tum:

```text
CSV / Excel Dataset
        ↓
Pandas
        ↓
Data Cleaning
        ↓
EDA
        ↓
Visualization
        ↓
Patterns / Outliers / Relationships
        ↓
Data-driven Insights
```

samajh aur implement kar sako ge.

Matplotlib mein `plot`, `scatter`, `bar`, `hist`, `boxplot`, subplots etc. core visualization tools hain. ([Matplotlib][1])

Seaborn inhi types ko statistical/data-oriented workflow mein convenient banata hai, especially DataFrames ke saath. ([Seaborn][2])

---

# 🗂️ Course Roadmap

| Module | Topic                   | Importance |
| ------ | ----------------------- | ---------: |
| 1      | Matplotlib Fundamentals |      ⭐⭐⭐⭐⭐ |
| 2      | Line Plot               |      ⭐⭐⭐⭐⭐ |
| 3      | Bar Plot                |      ⭐⭐⭐⭐⭐ |
| 4      | Scatter Plot            |      ⭐⭐⭐⭐⭐ |
| 5      | Histogram               |      ⭐⭐⭐⭐⭐ |
| 6      | Box Plot                |      ⭐⭐⭐⭐⭐ |
| 7      | Count Plot              |      ⭐⭐⭐⭐⭐ |
| 8      | Heatmap                 |      ⭐⭐⭐⭐⭐ |
| 9      | Pairplot                |       ⭐⭐⭐⭐ |
| 10     | Regression Plot         |       ⭐⭐⭐⭐ |
| 11     | Violin Plot             |       ⭐⭐⭐⭐ |
| 12     | Subplots                |      ⭐⭐⭐⭐⭐ |
| 13     | Complete EDA Project    |      ⭐⭐⭐⭐⭐ |

---

# 🧰 Module 0 — Setup

Install:

```bash
pip install pandas numpy matplotlib seaborn
```

Imports:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

sns.set_theme(style="whitegrid")
```

---

# 📈 Module 1 — Line Plot

## Real-world example: Company Monthly Sales

Suppose an e-commerce company has monthly sales data:

```python
import matplotlib.pyplot as plt

months = [
    "Jan", "Feb", "Mar", "Apr",
    "May", "Jun", "Jul", "Aug"
]

sales = [
    120000,
    135000,
    142000,
    155000,
    170000,
    165000,
    190000,
    210000
]

plt.plot(months, sales, marker="o")

plt.title("Monthly Company Sales")
plt.xlabel("Month")
plt.ylabel("Sales")

plt.show()
```

### 🧠 Roman Urdu

Line plot ka main kaam:

> **Time ke saath koi value kaise change ho rahi hai?**

Example:

```text
Month → Sales

Jan → 120K
Feb → 135K
Mar → 142K
...
Aug → 210K
```

Graph se trend immediately nazar aa jata hai.

### Real Data Science mein:

Use for:

* Monthly sales
* Daily revenue
* Website traffic
* Stock prices
* Temperature
* Users
* Profit

Seaborn mein:

```python
sns.lineplot(
    x=months,
    y=sales,
    marker="o"
)

plt.show()
```

Seaborn line plots continuous/time-related changes aur grouped relationships ko visualize karne ke liye designed hain. ([Seaborn][2])

### ❓ Interview Question

**Q:** Line plot kab use karte hain?

**Answer:**

> Jab data mein ordered/continuous progression ho, especially time-series data, aur humein trend ya change dekhna ho.

### 📝 Practice

Ek company ke:

```text
Jan = 50,000
Feb = 60,000
Mar = 55,000
Apr = 75,000
May = 90,000
```

ka line plot banao.

---

# 📊 Module 2 — Bar Plot

## Example: Product Sales

```python
products = [
    "Laptop",
    "Mobile",
    "Tablet",
    "Watch",
    "Headphones"
]

sales = [
    450,
    800,
    300,
    550,
    700
]

plt.bar(products, sales)

plt.title("Product Sales")
plt.xlabel("Product")
plt.ylabel("Units Sold")

plt.show()
```

### 🧠 Roman Urdu

Bar chart ka main purpose:

> **Different categories ko compare karna.**

```text
Laptop       █████
Mobile       █████████
Tablet       ███
Watch        ██████
Headphones   ████████
```

### Real company questions

Company pooch sakti hai:

> Sab se zyada products kis category ke sell hue?

Ya:

> Kis department ki revenue highest hai?

### Seaborn

```python
sns.barplot(
    x=products,
    y=sales
)

plt.show()
```

### ⚠️ Important

Bar plot:

```text
Category → Value
```

Line plot:

```text
Time/Order → Value
```

### ❓ Interview

**Q:** Bar chart aur histogram mein difference?

**Answer:**

**Bar chart:** categorical data compare karta hai.

**Histogram:** numerical data ki distribution show karta hai.

### 📝 Practice

5 departments ka employee count lekar bar chart banao:

```text
IT
HR
Sales
Marketing
Finance
```

---

# 🔵 Module 3 — Scatter Plot

## Example: Advertising Spend vs Sales

Ye real business analytics mein bohat important relationship question hai:

> Kya advertising spend increase hone se sales bhi increase hoti hain?

```python
advertising = [
    10, 20, 30, 40, 50,
    60, 70, 80, 90, 100
]

sales = [
    25, 32, 40, 45, 52,
    60, 66, 73, 82, 90
]

plt.scatter(advertising, sales)

plt.title("Advertising Spend vs Sales")
plt.xlabel("Advertising Spend")
plt.ylabel("Sales")

plt.show()
```

### 🧠 Roman Urdu

Har dot ek observation hai:

```text
Advertising
     ↑
100 |                 •
 80 |             •
 60 |         •
 40 |     •
 20 | •
    └──────────────────→ Sales
```

Tum relationship ka pattern dekh sakte ho.

Seaborn documentation bhi scatterplot ko two numeric variables ke relationship ko visualize karne ka fundamental tool batati hai. ([Seaborn][2])

### Seaborn

```python
sns.scatterplot(
    x=advertising,
    y=sales
)

plt.show()
```

### ⭐ Important

Scatter plot se **correlation ka idea** mil sakta hai, lekin:

> **Correlation ≠ Causation**

Agar advertising aur sales saath increase kar rahe hain, iska automatically matlab ye nahi ke advertising hi sales increase kar rahi hai.

### ❓ Interview

**Q:** Scatter plot kis liye use hota hai?

**Answer:**

> Do numerical variables ke relationship, pattern, clusters aur possible outliers ko inspect karne ke liye.

### 📝 Practice

Ye data use karo:

```python
study_hours = [1, 2, 3, 4, 5, 6, 7, 8]
marks = [40, 45, 52, 60, 65, 72, 80, 88]
```

Study hours vs marks scatter plot banao.

---

# 📊 Module 4 — Histogram

## Example: Customer Order Value

```python
order_values = [
    500, 550, 600, 620, 650,
    700, 720, 750, 800, 850,
    900, 950, 1000, 1200, 1500,
    1800, 2000
]

plt.hist(
    order_values,
    bins=6
)

plt.title("Customer Order Value Distribution")
plt.xlabel("Order Value")
plt.ylabel("Number of Customers")

plt.show()
```

### 🧠 Roman Urdu

Histogram ka question hota hai:

> **Data kis range mein kitna hai?**

Example:

```text
500–750      ███████
750–1000     █████
1000–1250    ███
1250–1500    █
1500–1750    █
1750–2000    ██
```

### Seaborn

```python
sns.histplot(
    order_values,
    bins=6,
    kde=True
)

plt.show()
```

Seaborn distribution plots mein histograms aur KDE jaise approaches provide karta hai. ([Seaborn][3])

### Histogram se tum identify kar sakte ho:

* Distribution
* Center
* Spread
* Skewness
* Possible unusual values

### ❓ Interview

**Q:** Histogram aur bar chart mein main difference?

**Answer:**

> Histogram numerical continuous data ki distribution show karta hai; bar chart categorical groups compare karta hai.

---

# 📦 Module 5 — Box Plot

## Example: Employee Salary

```python
salary = [
    30000,
    35000,
    38000,
    40000,
    42000,
    45000,
    47000,
    50000,
    52000,
    200000
]

plt.boxplot(salary)

plt.title("Employee Salary Distribution")
plt.ylabel("Salary")

plt.show()
```

### 🧠 Roman Urdu

Boxplot ka sabse important use:

> **Distribution + possible outliers ko quickly inspect karna.**

Agar:

```text
30000
35000
40000
45000
50000
52000
200000
```

mein `200000` baqi values se bohat door hai, boxplot usko visually highlight kar sakta hai.

Matplotlib boxplot ko statistical visualization ke liye provide karta hai. ([Matplotlib][4])

### Seaborn

```python
sns.boxplot(
    y=salary
)

plt.show()
```

### ❓ Interview

**Q:** Boxplot ka primary benefit?

**Answer:**

> Distribution ka compact summary aur potential outliers identify karna.

### 📝 Practice

Do departments compare karo:

```python
it_salary = [50000, 55000, 60000, 62000, 65000]
hr_salary = [40000, 45000, 47000, 50000, 52000]
```

Seaborn boxplot use karo.

---

# 🔢 Module 6 — Count Plot

Company ke customer records mein:

```python
customers = [
    "Male",
    "Female",
    "Male",
    "Female",
    "Female",
    "Male",
    "Male",
    "Female"
]

sns.countplot(x=customers)

plt.title("Customer Count")
plt.show()
```

### 🧠 Roman Urdu

`countplot()` ka simple meaning:

> **Har category kitni baar appear hui?**

For example:

```text
Male      ████
Female    ████
```

### Real DataFrame

```python
sns.countplot(
    data=df,
    x="Department"
)

plt.show()
```

Agar dataset mein:

```text
IT
IT
HR
Sales
IT
HR
Sales
Sales
```

hai to countplot automatically frequency show karega.

### ❓ Interview

**Q:** Countplot aur barplot mein difference?

**Answer:**

> Countplot observations ki frequency count karta hai, jabke barplot generally kisi numeric measure ka aggregation/estimate compare karta hai.

---

# 🔥 Module 7 — Heatmap

## Company Dataset

```python
data = {
    "Age": [22, 25, 28, 32, 35, 40],
    "Experience": [1, 3, 5, 7, 10, 15],
    "Salary": [30000, 40000, 50000, 60000, 75000, 100000],
    "Projects": [1, 2, 3, 5, 7, 10]
}

df = pd.DataFrame(data)
```

Correlation:

```python
correlation = df.corr()

sns.heatmap(
    correlation,
    annot=True
)

plt.title("Correlation Heatmap")
plt.show()
```

### 🧠 Roman Urdu

Heatmap mein:

```text
+1
 ↑
Strong positive

 0
 ↓
Weak/no linear relationship

-1
 ↓
Strong negative
```

### Data Science mein VERY IMPORTANT

Machine Learning se pehle:

```python
df.corr()
```

aur:

```python
sns.heatmap(df.corr(), annot=True)
```

bohat useful exploratory steps ho sakte hain.

### ❓ Interview

**Q:** Correlation value `0.95` ka kya matlab?

**Answer:**

> Do variables ke darmiyan strong positive linear association hai. Lekin is se causation prove nahi hoti.

---

# 🔥 Module 8 — Pairplot

Agar company dataset mein multiple numerical variables hain:

```python
df = sns.load_dataset("iris")

sns.pairplot(
    df,
    hue="species"
)

plt.show()
```

### 🧠 Roman Urdu

Pairplot basically:

> **Multiple numerical columns ke relationships ek saath inspect karne ka shortcut.**

Concept:

```text
          Age    Salary    Experience

Age        ●       ●          ●

Salary     ●       ●          ●

Experience ●       ●          ●
```

Seaborn pairwise relationships aur individual distributions ko ek visualization family mein examine karne ke tools provide karta hai. ([Seaborn][3])

### Real EDA mein

Suppose:

```text
Age
Salary
Experience
Sales
Profit
```

hain.

Tum quickly dekh sakte ho:

```python
sns.pairplot(df)
```

### ⚠️ Tip

Bohat large dataset ya bohat zyada columns par pairplot cluttered aur slow ho sakta hai.

---

# 📈 Module 9 — Regression Plot

Advertising vs Sales:

```python
advertising = [
    10, 20, 30, 40, 50,
    60, 70, 80, 90, 100
]

sales = [
    25, 32, 40, 45, 52,
    60, 66, 73, 82, 90
]

sns.regplot(
    x=advertising,
    y=sales
)

plt.title("Advertising vs Sales")
plt.show()
```

### 🧠 Roman Urdu

Ismein:

```text
• •
  •
    •
      •
       ─────────
```

dots = actual observations

line = estimated linear trend

Seaborn regression plots EDA mein noisy variables ke darmiyan simple relationship ko visually emphasize karne ke liye use hote hain; quantitative model evaluation ke liye dedicated statistical/modeling tools ki zarurat hoti hai. ([Seaborn][5])

### ❓ Interview

**Q:** Regression line ka purpose?

**Answer:**

> Variables ke relationship ka estimated linear trend visually show karna.

---

# 🎻 Module 10 — Violin Plot

Example:

```python
df = sns.load_dataset("tips")

sns.violinplot(
    data=df,
    x="day",
    y="total_bill"
)

plt.title("Bill Distribution by Day")
plt.show()
```

### 🧠 Roman Urdu

Violin plot:

> Distribution ki **shape/spread** ko category-wise compare karne ke liye useful hai.

Example:

```text
Monday       distribution
Tuesday      distribution
Wednesday    distribution
Thursday     distribution
Friday       distribution
```

Seaborn categorical visualization mein violin plots distribution ko categories ke across compare karne ke liye use kiye ja sakte hain. ([Seaborn][3])

---

# 🧩 Module 11 — Subplots

Real Data Science reports mein sirf ek graph nahi hota.

Example:

```python
months = ["Jan", "Feb", "Mar", "Apr"]

sales = [100, 150, 180, 220]
profit = [20, 30, 45, 60]

fig, axes = plt.subplots(
    1,
    2,
    figsize=(12, 5)
)

axes[0].plot(
    months,
    sales,
    marker="o"
)

axes[0].set_title("Sales")

axes[1].bar(
    months,
    profit
)

axes[1].set_title("Profit")

plt.tight_layout()
plt.show()
```

### Result concept

```text
┌───────────────────┬───────────────────┐
│                   │                   │
│      SALES        │      PROFIT       │
│                   │                   │
│                   │                   │
└───────────────────┴───────────────────┘
```

Matplotlib ka `Figure` aur `Axes` system multiple plots ko ek figure mein organize karne ke liye core concept hai. ([Matplotlib][1])

---

# 🏢 Module 12 — Complete Company EDA Project

Ab sab concepts **ek hi dataset** par apply karte hain.

Suppose company ka CSV:

```text
ecommerce_sales.csv
```

columns:

```text
Order_Date
Product
Category
Sales
Profit
Quantity
Customer_Age
Discount
Region
```

Load:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("ecommerce_sales.csv")

print(df.head())
print(df.info())
print(df.describe())
```

---

## Step 1 — Sales Distribution

```python
sns.histplot(
    data=df,
    x="Sales",
    kde=True
)

plt.title("Sales Distribution")
plt.show()
```

**Question:**

> Most orders ki sales kis range mein hain?

---

## Step 2 — Category Sales

```python
sns.barplot(
    data=df,
    x="Category",
    y="Sales"
)

plt.title("Average Sales by Category")
plt.xticks(rotation=45)

plt.show()
```

**Question:**

> Kis category ka average sales level higher hai?

---

## Step 3 — Quantity vs Sales

```python
sns.scatterplot(
    data=df,
    x="Quantity",
    y="Sales"
)

plt.title("Quantity vs Sales")
plt.show()
```

**Question:**

> Quantity aur Sales ke darmiyan kya pattern nazar aa raha hai?

---

## Step 4 — Sales Outliers

```python
sns.boxplot(
    data=df,
    y="Sales"
)

plt.title("Sales Outliers")
plt.show()
```

**Question:**

> Kya unusually high/low sales observations hain?

---

## Step 5 — Region Count

```python
sns.countplot(
    data=df,
    x="Region"
)

plt.title("Orders by Region")
plt.xticks(rotation=45)

plt.show()
```

**Question:**

> Kis region mein records/orders zyada hain?

---

## Step 6 — Correlation

```python
numeric_df = df[
    [
        "Sales",
        "Profit",
        "Quantity",
        "Customer_Age",
        "Discount"
    ]
]

corr = numeric_df.corr()

sns.heatmap(
    corr,
    annot=True,
    fmt=".2f"
)

plt.title("Feature Correlation")
plt.show()
```

**Question:**

> Sales aur Profit ka relationship kaisa hai?

---

# 🧠 Real Data Science Workflow

Ab tum visualization ko isolated commands ki tarah nahi, **workflow** ki tarah samjho:

```text
              CSV
               │
               ▼
          pd.read_csv()
               │
               ▼
         df.head()
         df.info()
         df.describe()
               │
               ▼
        DATA CLEANING
               │
       ┌───────┴────────┐
       ▼                ▼
   Numerical        Categorical
       │                │
       ▼                ▼
   Histogram        Countplot
   Boxplot          Barplot
       │
       ▼
    Relationships
       │
       ├── Scatter
       ├── Regplot
       ├── Pairplot
       └── Heatmap
       │
       ▼
     INSIGHTS
```

---

# 🎯 Sabse Important Decision Rule

Graph choose karne ke liye ye **cheat sheet** yaad kar lo:

```text
Question                         Plot
────────────────────────────────────────────
Time ke saath change?            Line
Categories compare karni hain?  Bar
2 numeric variables relation?   Scatter
Distribution dekhni hai?        Histogram
Outliers check karne hain?      Boxplot
Category frequency?              Countplot
Correlation check?               Heatmap
Many variables relationships?   Pairplot
Trend + regression?              Regplot
Distribution by category?       Violin
Multiple graphs together?       Subplots
```

---

# 🔥 10 Plots Jo Tumhein MUST Master Karne Chahiye

Agar tum beginner ho aur **sab kuch ek saath nahi seekhna**, to ye order follow karo:

### Level 1

```text
1️⃣ Line Plot
2️⃣ Bar Plot
3️⃣ Scatter Plot
4️⃣ Histogram
5️⃣ Box Plot
```

### Level 2

```text
6️⃣ Count Plot
7️⃣ Heatmap
8️⃣ Pairplot
```

### Level 3

```text
9️⃣ Regression Plot
🔟 Violin Plot
```

### Alongside Matplotlib

```text
plt.figure()
plt.subplots()
plt.title()
plt.xlabel()
plt.ylabel()
plt.legend()
plt.grid()
plt.xticks()
plt.yticks()
plt.tight_layout()
plt.savefig()
```

Matplotlib ki official documentation mein lines, bars, scatter, histograms, boxplots, violin plots aur subplot layouts sab major plotting capabilities ke taur par covered hain. ([Matplotlib][6])

---

# 💼 Interview Questions — Final Set

### Beginner

**1. Matplotlib kya hai?**

Python ki visualization library jo graphs aur charts create karne ke liye use hoti hai.

**2. Seaborn kya hai?**

Statistical data visualization library jo Matplotlib ke upar built hai aur DataFrame-oriented visualization ko convenient banati hai.

**3. Line plot kab use hota hai?**

Trends/ordered continuous data ke liye.

**4. Bar plot kab use hota hai?**

Categories compare karne ke liye.

**5. Scatter plot kya show karta hai?**

Do numerical variables ka relationship.

---

### Intermediate

**6. Histogram aur bar chart mein difference?**

Histogram numerical distribution; bar chart categorical comparison.

**7. Boxplot kis liye use hota hai?**

Distribution aur potential outliers inspect karne ke liye.

**8. Heatmap kis liye use hota hai?**

Matrix values, especially correlation matrix, ko visually inspect karne ke liye.

**9. Pairplot kya karta hai?**

Multiple variables ke pairwise relationships/distributions ko ek visualization mein examine karta hai.

**10. Correlation `-0.8` ka kya matlab?**

Strong negative linear association indicate karta hai; causation prove nahi karta.

---

# 📝 Final Practice Project

Ab tumhara **real Data Science assignment**:

### Dataset

Create/load an e-commerce dataset with:

```text
Order_Date
Product
Category
Sales
Profit
Quantity
Customer_Age
Discount
Region
```

### Tumhein ye 10 graphs banane hain:

```text
1. Monthly Sales              → Line Plot

2. Category Sales             → Bar Plot

3. Quantity vs Sales          → Scatter Plot

4. Sales Distribution         → Histogram

5. Sales Outliers             → Box Plot

6. Orders by Region           → Count Plot

7. Numeric Correlations       → Heatmap

8. Multiple Variables         → Pairplot

9. Quantity vs Sales Trend    → Regplot

10. Sales by Category Spread  → Violin Plot
```
