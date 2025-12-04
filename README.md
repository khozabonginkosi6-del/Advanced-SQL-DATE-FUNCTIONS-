# 📘 SQL Practice Queries — Date & Time Functions

## 📌 Summary of the Case Study
This case study demonstrates how SQL **date and time functions** can be applied to manipulate, format, and analyze temporal data across multiple tables. The project focused on adding or subtracting time intervals, calculating differences, extracting specific parts of dates, formatting date outputs, and constructing complete dates from individual components. The goal was to show how SQL can transform raw date/time values into **business insights** for scheduling, tracking, and reporting.

---

## 🔍 How the Case Study Was Done
1. **Dataset Exploration**
   - Tables used:
     - `employees (emp_id, name, hire_date)`
     - `students (student_id, name, dob)`
     - `events (event_id, event_name, event_date)`
     - `invoices (invoice_id, issue_date, due_date)`
     - `courses (course_id, name, start_date)`
     - `memberships (member_id, start_year, start_month, start_day)`
     - `subscriptions (sub_id, plan, renewal_date)`
     - `orders (order_id, order_date)`
     - `trainings (training_id, topic, training_date)`
     - `blog_posts (post_id, title, published_on)`
     - `drivers (driver_id, license_expiry)`
     - `messages (message_id, sent_timestamp)`
     - `returns (return_id, return_date)`
     - `assignments (assign_id, assigned_on)`
     - `meetings (meeting_id, scheduled_time)`

2. **SQL Query Development**
   - **DATEADD** → Added intervals (e.g., 6 months to hire date, 1 year to renewal date, 15 days to return date).  
   - **DATEDIFF** → Calculated differences (e.g., age in days, days until events, days between invoice issue and due dates, seconds since messages sent).  
   - **DATE_PART** → Extracted components (year from training dates, hour and minute from blog posts).  
   - **TO_VARCHAR** → Formatted dates into readable strings (e.g., “Month YYYY”, “November 25, 2025 at 09:30 AM”).  
   - **DATE_FROM_PARTS / TO_DATE** → Constructed full dates from year, month, day parts or converted strings into proper date formats.  

3. **Techniques Applied**
   - **Temporal arithmetic** → Adding/subtracting months, years, days.  
   - **Difference calculations** → Measuring elapsed or remaining time.  
   - **Date extraction** → Pulling specific components for reporting.  
   - **Formatting** → Converting raw dates into human-readable formats.  
   - **Construction** → Building valid dates from fragmented data.  

---

## 📊 Insights Found
- Employee hire dates can be extended to project **future milestones** (e.g., 6-month reviews).  
- Student ages calculated in days provided **precise demographic insights**.  
- Event countdowns highlighted **time remaining for scheduling and preparation**.  
- Invoice analysis revealed **payment timelines and due date gaps**.  
- Course start dates formatted into “Month YYYY” improved **report readability**.  
- Membership data reconstructed into full dates ensured **data consistency**.  
- Subscription renewals extended by 1 year supported **customer retention tracking**.  
- Order analysis showed **days since purchase**, useful for delivery and follow-up.  
- Training year extraction enabled **annual reporting**.  
- Blog post timestamps revealed **publishing patterns by hour and minute**.  
- Driver license expiry analysis flagged **upcoming renewals**.  
- Message timestamps measured **real-time communication delays**.  
- Return restock dates supported **inventory management**.  
- Assignment string-to-date conversion improved **data integrity**.  
- Meeting time formatting provided **clear scheduling outputs**.  

---

## 🎯 Summary of Findings
By applying SQL date and time functions, the project uncovered:  
- How to **track timelines** across employees, students, and customers.  
- Methods to **calculate differences** for events, invoices, and orders.  
- Techniques to **format and present dates** for reporting clarity.  
- Ways to **construct valid dates** from fragmented or string-based inputs.  

This demonstrates how SQL can deliver **business intelligence** by turning raw date/time values into actionable insights for **operations, scheduling, and customer management**.

---

## 🛠️ Tools Used
- **SQL-compatible environments** (Snowflake, PostgreSQL, SQL Server, Oracle, MySQL)  
- **SQL functions** (DATEADD, DATEDIFF, DATE_PART, TO_VARCHAR, DATE_FROM_PARTS, TO_DATE)  
- **Optional Visualization Tools**: Power BI, Excel (pivot tables, dashboards)  

