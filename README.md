# 📊 Sales Tracking Dashboard — Google Forms + Google Sheets + Looker Studio

## Overview
This project is a **live sales-tracking system** built entirely with free Google tools. Sales representatives record every sale using a Google Form. Their answers are saved automatically into a Google Sheet, where a formula instantly calculates the total sale value. That same sheet feeds a **Looker Studio dashboard**, which refreshes automatically — so new sales appear on the dashboard within about 15 minutes, with no manual work.

**Data flow:**
```
Google Form  →  Google Sheet (auto formula)  →  Looker Studio Dashboard (auto-refresh)
```

## 🔗 Live Project Links
| Resource | Link |
|---|---|
| 📝 Google Form (data entry) | [forms.gle/hyqEd73EtJ8g1LZC8](https://forms.gle/hyqEd73EtJ8g1LZC8) |
| 📄 Google Sheet (live responses) | [View Sheet](https://docs.google.com/spreadsheets/d/15X9-YDlK1z7xCOSTMDqAQ6S22j4wsbmehtGlKpqZhCk/edit?usp=sharing) |
| 📈 Looker Studio Dashboard | [View Dashboard](https://datastudio.google.com/s/m7cZLCI1Sgo) |

## 🛠️ Tools Used
- Google Forms — data collection
- Google Sheets — data storage + calculation
- Looker Studio (Google Data Studio) — data visualization

## 📁 Form Fields
| Field | Type | Rule |
|---|---|---|
| Sales Rep Name | Dropdown | Required |
| Customer Name | Short answer | Required |
| Products | Dropdown | Required |
| Quantity | Short answer | Number > 0 |
| Unit Price | Short answer | Number > 0 |
| Place | Dropdown | Required |
| Notes | Short answer (optional) | — |

**Response validation:** Quantity and Unit Price fields use Google Forms' number validation (`Greater than 0`) with a custom error message: *"Please enter a number greater than 0."* This blocks negative or zero values.

**Dropdowns for consistency:** Sales Rep Name and Products are Dropdown fields (not free text) to prevent typos and keep names consistent across every row — this is essential for accurate grouping and totals in the dashboard.

**Form settings enabled:**
- ✅ Collect email addresses
- ✅ Allow response editing (reps can fix mistakes without duplicating rows)
- ✅ Send responders a copy of their response
- ✅ Unlimited submissions (no "limit to 1 response")

## 🧮 Key Formula
The **Total Sales** column is calculated automatically for every new row — no manual dragging required:

```
=ARRAYFORMULA(IF(G2:G="","",F2:F*G2:G))
```

This multiplies **Quantity (column F) × Unit Price (column G)** instantly whenever a new form response is submitted.

## 📊 Dashboard Charts
The Looker Studio dashboard includes:
- **Column chart** — Total Sales by Sales Rep
- **Pie chart** — Total Sales share by Product (Laptop, TV, Printer, Monitor)
- **Bar chart** — Top performing sales reps by revenue
- **Location breakdown** — Sales by Place (Cairo, Giza, Alex)

## 🔄 Auto-Refresh
The dashboard is connected to Google Sheets with **data freshness set to every 15 minutes** (the fastest refresh rate available for this connector). A sales rep submits a sale on the form, and it appears on the dashboard automatically — no manual refresh needed.

## 🎨 Customization
- Theme and color palette can be changed via **Theme and Layout** in Looker Studio's editor.
- The company logo can be added via **Insert → Image** in the report editor.

## 📸 Screenshot
Add your dashboard screenshot here:
```
![Sales Looker Studio Dashboard](Sales%20-%20Looker%20Studio.jpg)
```

---

## 👨‍💻 Author

**Haitham Abobakr**

Senior Computer Instructor | Data Analytics | Power BI | AI | eLearning

This project is part of my **Data Analytics & Business Intelligence portfolio**.

---

⭐ If you find this project useful, feel free to explore the repository and connect with me on GitHub.
