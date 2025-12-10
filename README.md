# stack-overflow-developer-survey

# Stack Overflow Developer Survey – Technology Trends Analysis  
**Author:** Anita C. Carrasco  
**Tools:** Google Sheets, Looker Studio, Data Visualization, Data Wrangling

## 📌 Overview
This project analyzes the Stack Overflow Developer Survey to uncover current and emerging technology trends across programming languages, databases, platforms, and developer demographics. The goal is to translate raw survey data into actionable insights for technology leaders, educators, and teams making strategic decisions around hiring, training, and tooling.

Three interactive dashboards were created using Looker Studio:

- **Current Technology Usage**
- **Future Technology Trends**
- **Demographics**

These dashboards are supported by extensive data wrangling, including the transformation of multi-select survey fields into structured datasets using SPLIT and FLATTEN operations.

---

## 📊 Key Insights
### **Programming Languages**
- JavaScript, SQL, and Python lead current usage.
- Python and TypeScript show the strongest future demand.
- Developer interest aligns with modern workflows in AI, automation, and scalable web development.

### **Databases**
- PostgreSQL dominates current and future adoption.
- Redis shows the strongest forward momentum, driven by real-time data needs.
- MySQL and SQLite remain widely used due to legacy and simplicity.

### **Platforms**
- AWS, Google Cloud, and Azure dominate both usage and interest.
- Strong growth in modern hosting tools such as Vercel, Firebase, and Cloudflare indicates a shift toward developer-friendly deployment.

### **Demographics**
- Most respondents fall between ages 25–34.
- The global distribution reinforces that these trends generalize across regions.
- The majority hold a bachelor’s or master’s degree, influencing tool adoption patterns.

---

## 🧹 Data Wrangling
To transform multi-answer fields like `LanguageHaveWorkedWith` and `DatabaseWantToWorkWith`, Google Sheets formulas were used:

```gs
=ARRAYFORMULA(
  QUERY(
    SPLIT(
      FLATTEN(Raw!$A2:$A & "♦" & SPLIT(Raw!$W2:$W, ";")),
      "♦"
    ),
    "select * where Col2 is not null", 0
  )
)
```

This created clean, analysis-ready tables for each technology category.

---

## 🖥 Dashboards
The interactive dashboards visualize:

- Top 10 languages, databases, platforms, and frameworks  
- Future technology preferences  
- Age distribution, country distribution, and education levels  

These dashboards support decision-making in workforce planning, technology adoption, and curriculum design.

---

## 📌 Files Included
- `analysis_presentation.pdf` — Final project presentation  
- `cleaned_datasets/` — Data tables after wrangling  
- `dashboard_screenshots/` — Images of all Looker Studio dashboards  
- `README.md` — Project documentation (this file)

---

## 🚀 Conclusion
This project provides a clear view of how developers work today and what technologies they expect to adopt next. The analysis highlights the importance of cloud ecosystems, modern frameworks, and data skills — all critical for staying competitive in today’s tech landscape.

