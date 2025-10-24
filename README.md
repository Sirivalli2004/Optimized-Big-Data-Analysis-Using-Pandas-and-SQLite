# Optimized-Big-Data-Analysis-Using-Pandas-and-SQLite
---

```markdown
# 🚀 Optimized Big Data Analysis using Pandas & SQLite  

### 📘 Project by [Thandu Sirivalli](https://github.com/)  
B.Tech – Electronics and Communication Engineering, NIT Trichy  

---

## 🧩 Overview  

This project demonstrates how to handle and analyze **large-scale datasets (3.9 GB)** that cannot fit into system memory using **Pandas (Python)** and **SQLite**.  
By applying **chunk-based data processing**, SQL-based aggregation, and interactive visualization using **Plotly**, this project shows how businesses can derive insights efficiently from massive datasets — an essential skill in **Digital Strategy and Data Analytics**.

---

## 🎯 Objectives  

- Efficiently load and process **large datasets** without memory crashes.  
- Use **SQLite** as a lightweight database for scalable querying.  
- Apply **SQL-based data aggregation** directly within Python.  
- Visualize insights interactively using **Plotly**.  
- Demonstrate **data-driven problem-solving** for strategic decision-making.  

---

## 🧠 Problem Background  

Loading large datasets directly into Pandas can cause memory overflow.  
To overcome this, we:  
- Divide the data into **chunks** using the `chunksize` parameter.  
- Insert each chunk into an **SQLite database**.  
- Run **SQL queries** to perform aggregations and analytics.  
- Visualize the results using **Plotly** for actionable insights.

---

## ⚙️ Tech Stack  

| Category | Tools / Libraries |
|-----------|-------------------|
| Programming Language | Python |
| Data Handling | Pandas |
| Database | SQLite |
| Visualization | Plotly |
| Environment | Jupyter Notebook / Google Colab |

---

## 📂 Project Structure  

```

Optimized_Big_Data_Analysis_Pandas_SQLite/
│
├── NYC_311_Service_Requests.csv        # Sample dataset
├── nyc311.db                           # SQLite database created
├── Optimized_Big_Data_Analysis_Pandas_SQLite.ipynb   # Main notebook
└── README.md                           # Project documentation

````

---

## 🪜 Step-by-Step Workflow  

1. **Import Libraries**
   ```python
   import pandas as pd
   import sqlite3
   import plotly.express as px
````

2. **Read Dataset in Chunks**

   ```python
   chunksize = 100000
   for chunk in pd.read_csv("NYC_311_Service_Requests.csv", chunksize=chunksize):
       chunk.to_sql("complaints", conn, if_exists="append", index=False)
   ```

3. **Run SQL Queries**

   ```python
   query = """
   SELECT "Complaint Type", COUNT(*) AS Total
   FROM complaints
   GROUP BY "Complaint Type"
   ORDER BY Total DESC
   LIMIT 10;
   """
   df = pd.read_sql_query(query, conn)
   ```

4. **Visualize Insights**

   ```python
   fig = px.bar(df, x="Complaint Type", y="Total", title="Top 10 Complaint Types in NYC")
   fig.show()
   ```

---

## 📊 Sample Outputs

| Analysis Type         | Visualization |
| --------------------- | ------------- |
| Top Complaint Types   | 📊 Bar Chart  |
| Complaints by Borough | 🥧 Pie Chart  |
| Monthly Trend         | 📈 Line Chart |

---

## 🧾 Results

* Efficiently handled a **3.9GB dataset** without memory overload.
* Performed **SQL-based aggregations** directly from Python.
* Built **interactive visualizations** for quick business insights.
* Demonstrated **data optimization and analytical thinking** aligned with digital transformation strategy.

---

## 💡 Key Learnings

* Working with **big data using limited system memory**.
* Using **SQLite as a temporary analytical data store**.
* Enhancing insights with **interactive Plotly dashboards**.
* Strengthened problem-solving and visualization skills for roles in **Data Strategy, Analytics, and Consulting**.

---


---

## 🤝 Acknowledgements

Dataset Source: [NYC Open Data Portal](https://data.cityofnewyork.us/)
Developed under guidance from NIT Trichy academic and research resources.

---

## 📫 Contact

**Thandu Sirivalli**
📧 [sirivalligoud141@gmail.com](mailto:sirivalligoud141@gmail.com)
📞 +91 9491089370
🎓 Head – Marketing Team, Probe'25, NIT Trichy
🌐 [LinkedIn](https://www.linkedin.com/) | [GitHub](https://github.com/)

---

