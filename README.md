# ola-dashboard-powerbi-sql-dashboard
End-to-end Data Analytics and Business Intelligence project built using Excel, SQL, and Power BI to analyze OLA ride-booking data for Bengaluru city. The project includes ride trends, revenue analysis, customer behavior, cancellations, vehicle performance, ratings, and interactive dashboards with KPI tracking and business insights.
# 🚖 OLA Data Analyst Project – Complete Dashboard & Business Intelligence Analysis

## 📌 Project Overview

The OLA Data Analyst Project is an end-to-end **Business Intelligence and Data Analytics Project** developed using **Microsoft Excel, SQL, and Power BI** to analyze ride-booking operations in Bengaluru city.

This project contains **1 lakh ride-booking records** for one month and focuses on analyzing:

- Ride booking trends
- Customer behavior
- Vehicle performance
- Revenue generation
- Cancellation patterns
- Driver & customer ratings
- Payment method analysis
- Operational efficiency

The main objective of this project is to understand how ride-booking companies like Ola use data analytics to:

- Improve customer satisfaction
- Reduce cancellations
- Optimize vehicle allocation
- Increase business revenue
- Monitor operational performance

---

# 🎯 Project Objectives

The major objectives of this project are:

✔ Analyze overall booking performance  
✔ Track successful and cancelled rides  
✔ Study customer and driver behavior  
✔ Identify peak booking periods  
✔ Analyze vehicle performance  
✔ Understand revenue patterns  
✔ Compare payment methods  
✔ Measure customer satisfaction through ratings  
✔ Build interactive dashboards for business insights  

---

# 🛠 Tools & Technologies Used

## 📊 Microsoft Excel
Used for:
- Data cleaning
- Removing duplicates
- Data formatting
- Initial preprocessing
- Data validation

## 🗄 SQL
Used for:
- Data querying
- Data analysis
- Creating business views
- Aggregation and filtering
- KPI calculations

## 📈 Power BI
Used for:
- Dashboard development
- Data visualization
- KPI tracking
- Interactive reporting
- Business storytelling

---

# 📂 Dataset Information

| Category | Details |
|---|---|
| 📌 Total Records | 100,000 |
| 📍 City | Bengaluru |
| 📅 Time Duration | 1 Month |
| 🚖 Project Type | Ride Booking Analytics |
| 🏢 Industry | Transportation & Mobility |

---

# 🧾 Dataset Columns

| Column Name | Description |
|---|---|
| Date | Ride booking date |
| Time | Ride booking time |
| Booking_ID | Unique ride booking ID |
| Booking_Status | Ride status |
| Customer_ID | Unique customer identifier |
| Vehicle_Type | Type of vehicle booked |
| Pickup_Location | Pickup location |
| Drop_Location | Drop location |
| V_TAT | Vehicle arrival time |
| C_TAT | Customer waiting time |
| Cancelled_Rides_by_Customer | Customer cancellation status |
| Cancelled_Rides_by_Driver | Driver cancellation status |
| Incomplete_Rides | Incomplete ride status |
| Incomplete_Rides_Reason | Reason for incomplete ride |
| Booking_Value | Ride fare amount |
| Payment_Method | Payment mode |
| Ride_Distance | Distance travelled |
| Driver_Ratings | Driver rating |
| Customer_Rating | Customer rating |

---

# 🚘 Vehicle Types Included

- Auto
- Mini
- Bike
- eBike
- Prime Sedan
- Prime SUV
- Prime Plus

These categories help analyze:
- Customer preferences
- Ride affordability
- Premium ride demand
- Revenue generation

---

# ⚙ Dataset Business Logic

## 📌 Booking Status Distribution

| Booking Status | Percentage |
|---|---|
| ✅ Successful Rides | 62% |
| ❌ Customer Cancelled | Less than 7% |
| 🚫 Driver Cancelled | Less than 18% |
| ⚠ Incomplete Rides | Less than 6% |

---

## 📅 Weekend Demand Increase

Ride bookings are intentionally higher on:
- Saturdays
- Sundays
- Match Days

This simulates real-world ride demand spikes.

---

## 💰 Dynamic Pricing Logic

Booking values are higher during weekends because:
- Demand increases
- Surge pricing activates
- Long-distance rides increase

---

## 💵 Booking Value Distribution

| Fare Range | Percentage |
|---|---|
| ₹0 – ₹500 | 70% |
| ₹500 – ₹1000 | 28% |
| Above ₹1000 | Remaining |

This creates realistic fare distribution.

---

# ❌ Customer Cancellation Reasons

- Driver not moving toward pickup
- Driver asked to cancel
- AC not working
- Change of plans
- Wrong address

---

# 🚫 Driver Cancellation Reasons

- Personal & car-related issues
- Customer-related issue
- Customer was sick
- More passengers than allowed

---

# ⚠ Incomplete Ride Reasons

- Customer demand
- Vehicle breakdown
- Other issue

---

# 🗄 SQL Analysis Performed

## 1️⃣ Successful Bookings Analysis

```sql
SELECT *
FROM bookings
WHERE Booking_Status = 'Success';
```

---

## 2️⃣ Average Ride Distance by Vehicle Type

```sql
SELECT Vehicle_Type,
AVG(Ride_Distance) AS avg_distance
FROM bookings
GROUP BY Vehicle_Type;
```

---

## 3️⃣ Customer Cancellation Analysis

```sql
SELECT COUNT(*)
FROM bookings
WHERE Booking_Status = 'Cancelled by Customer';
```

---

## 4️⃣ Top 5 Customers Analysis

```sql
SELECT Customer_ID,
COUNT(Booking_ID) AS total_rides
FROM bookings
GROUP BY Customer_ID
ORDER BY total_rides DESC
LIMIT 5;
```

---

## 5️⃣ Driver Cancellation Analysis

```sql
SELECT COUNT(*)
FROM bookings
WHERE Cancelled_Rides_by_Driver =
'Personal & Car related issue';
```

---

## 6️⃣ Driver Ratings Analysis

```sql
SELECT MAX(Driver_Ratings),
MIN(Driver_Ratings)
FROM bookings
WHERE Vehicle_Type = 'Prime Sedan';
```

---

## 7️⃣ UPI Payment Analysis

```sql
SELECT *
FROM bookings
WHERE Payment_Method = 'UPI';
```

---

## 8️⃣ Average Customer Rating Analysis

```sql
SELECT Vehicle_Type,
AVG(Customer_Rating)
FROM bookings
GROUP BY Vehicle_Type;
```

---

## 9️⃣ Total Revenue Analysis

```sql
SELECT SUM(Booking_Value)
FROM bookings
WHERE Booking_Status = 'Success';
```

---

## 🔟 Incomplete Ride Analysis

```sql
SELECT Booking_ID,
Incomplete_Rides_Reason
FROM bookings
WHERE Incomplete_Rides = 'Yes';
```

---

# 📊 Power BI Dashboard Structure

The Power BI dashboard is divided into 5 analytical pages.

---

# 📍 1. Overall Dashboard

## KPIs Included
- Total Bookings
- Successful Rides
- Cancelled Rides
- Incomplete Rides
- Total Revenue
- Success Rate
- Average Ride Distance

## Visuals Used
- KPI Cards
- Line Charts
- Donut Charts
- Daily Ride Trend Charts

## Key Insights
- Weekend bookings are higher
- Evening hours have peak demand
- Successful rides dominate total bookings
- Revenue increases during surge periods

## 🖼 Dashboard Preview
Add Overall Dashboard Screenshot Here

---

# 🚘 2. Vehicle Type Dashboard

## KPIs Included
- Total Bookings by Vehicle
- Vehicle-wise Revenue
- Average Ride Distance
- Vehicle Usage %

## Visuals Used
- Bar Charts
- Pie Charts
- Vehicle Comparison Charts

## Key Insights
- Mini and Bike have highest bookings
- Prime Sedan generates higher revenue
- Premium rides cover longer distances

## 🖼 Dashboard Preview
Add Vehicle Type Dashboard Screenshot Here

---

# 💰 3. Revenue Dashboard

## KPIs Included
- Total Revenue
- Average Booking Value
- Weekend Revenue
- Revenue by Payment Method

## Visuals Used
- Revenue Trend Charts
- Stacked Bar Charts
- Customer Leaderboards

## Key Insights
- UPI is the most preferred payment method
- Weekend revenue is highest
- Premium rides generate higher profits

## 🖼 Dashboard Preview
Add Revenue Dashboard Screenshot Here

---

# ❌ 4. Cancellation Dashboard

## KPIs Included
- Customer Cancellation %
- Driver Cancellation %
- Incomplete Ride %
- Most Common Cancellation Reason

## Visuals Used
- Donut Charts
- Cancellation Trend Graphs
- Reason-wise Bar Charts

## Key Insights
- Driver delays cause major customer cancellations
- Personal vehicle issues are major driver-side problems
- Incomplete rides impact customer experience

## 🖼 Dashboard Preview
Add Cancellation Dashboard Screenshot Here

---

# ⭐ 5. Ratings Dashboard

## KPIs Included
- Average Driver Rating
- Average Customer Rating
- Highest Rated Vehicle
- Lowest Rated Vehicle

## Visuals Used
- Scatter Plot
- Histogram
- Box Plot

## Key Insights
- Prime Sedan receives better ratings
- Better service increases customer loyalty
- Low ratings indicate operational issues

## 🖼 Dashboard Preview
Add Ratings Dashboard Screenshot Here

---

# 📐 DAX Measures & Formulas Used

## Total Bookings

```DAX
Total Bookings = COUNT(bookings[Booking_ID])
```

## Successful Rides

```DAX
Successful Rides =
CALCULATE(
COUNT(bookings[Booking_ID]),
bookings[Booking_Status] = "Success"
)
```

## Total Revenue

```DAX
Total Revenue = SUM(bookings[Booking_Value])
```

## Average Ride Distance

```DAX
Average Ride Distance =
AVERAGE(bookings[Ride_Distance])
```

## Customer Cancellation %

```DAX
Customer Cancellation % =
DIVIDE(
COUNTROWS(FILTER(bookings,
bookings[Booking_Status] =
"Cancelled by Customer")),
COUNTROWS(bookings)
)
```

## Average Driver Rating

```DAX
Average Driver Rating =
AVERAGE(bookings[Driver_Ratings])
```

---

# 🛠 Steps Followed In This Project

## ✅ Step 1 – Data Collection
Generated 1 lakh ride-booking records using realistic business logic.

## ✅ Step 2 – Data Cleaning
Performed:
- Formatting
- Duplicate removal
- Data validation

## ✅ Step 3 – SQL Analysis
Performed:
- Aggregations
- Filtering
- Business analysis queries

## ✅ Step 4 – Data Import in Power BI
Imported cleaned dataset into Power BI.

## ✅ Step 5 – Data Modeling
Created:
- Relationships
- Calculated columns
- DAX measures

## ✅ Step 6 – Dashboard Development
Built:
- Interactive visuals
- KPI cards
- Trend analysis pages

## ✅ Step 7 – Business Insights
Generated insights for:
- Revenue
- Customer behavior
- Vehicle performance
- Cancellations
- Ratings

---

# ⚠ Challenges Faced During The Project

- Managing large datasets
- Maintaining realistic booking distributions
- Data cleaning
- Creating interactive dashboards
- Writing optimized SQL queries

---

# 🧠 Skills Demonstrated

## 💻 Technical Skills
- SQL
- Power BI
- Excel
- Data Cleaning
- DAX
- Dashboard Development

## 📊 Analytical Skills
- Trend Analysis
- Revenue Analysis
- Customer Behavior Analysis
- KPI Analysis
- Business Intelligence

---

# 🌟 Why This Project Is Important

## 🚖 Real-World Business Simulation
This project simulates how real ride-booking companies analyze operational data.

## 💼 Strong Portfolio Project
This project demonstrates:
- SQL expertise
- Power BI dashboard skills
- Business Intelligence knowledge
- Data storytelling ability

## 📈 Industry-Relevant Analysis
The project includes:
- Revenue analysis
- Cancellation tracking
- Customer satisfaction analysis
- Vehicle performance analysis

These are commonly used in real companies.

---

# 🏁 Conclusion

The OLA Data Analyst Project is a complete Business Intelligence and Data Analytics solution developed using Excel, SQL, and Power BI.

The project successfully analyzes:

- Ride booking trends
- Customer behavior
- Revenue generation
- Vehicle performance
- Cancellation patterns
- Service quality

This dashboard helps businesses make data-driven decisions to improve:

✔ Operational efficiency  
✔ Customer satisfaction  
✔ Revenue growth  

The project reflects strong analytical thinking, SQL expertise, dashboard-building capability, and business understanding, making it an excellent portfolio project for aspiring Data Analysts and Business Intelligence professionals.

---

# 📌 Author

## Vivek Gautam
Data Analyst | SQL | Power BI | Excel | Business Intelligence

