📘 SQL Practice Queries — Date & Time Functions
📌 Overview
This project demonstrates SQL queries that manipulate and format date and time values across multiple tables. The examples cover:

Adding or subtracting time intervals (DATEADD)

Calculating differences (DATEDIFF)

Extracting parts of dates (DATE_PART)

Formatting dates (TO_VARCHAR)

Constructing dates (DATE_FROM_PARTS, TO_DATE)

🛠️ Requirements
SQL-compatible database (Snowflake, PostgreSQL, SQL Server, Oracle, MySQL with slight syntax adjustments)

Tables used in examples:

employees (emp_id, name, hire_date)

students (student_id, name, dob)

events (event_id, event_name, event_date)

invoices (invoice_id, issue_date, due_date)

courses (course_id, name, start_date)

memberships (member_id, start_year, start_month, start_day)

subscriptions (sub_id, plan, renewal_date)

orders (order_id, order_date)

trainings (training_id, topic, training_date)

blog_posts (post_id, title, published_on)

drivers (driver_id, license_expiry)

messages (message_id, sent_timestamp)

returns (return_id, return_date)

assignments (assign_id, assigned_on)

meetings (meeting_id, scheduled_time)

📂 Queries
1. 👔 Employees – Add 6 Months to Hire Date
sql
SELECT emp_id, name, hire_date,
       DATEADD(month, 6, hire_date) AS hire_plus_6_months
FROM employees;
Adds 6 months to each employee’s hire date.

2. 🎓 Students – Age in Days
sql
SELECT student_id, name,
       DATEDIFF(day, dob, CURRENT_DATE) AS age_in_days
FROM students;
Calculates each student’s age in days.

3. 📅 Events – Days Remaining
sql
SELECT event_id, event_name,
       DATEDIFF(day, CURRENT_DATE, event_date) AS days_remaining
FROM events;
Shows how many days remain until each event.

4. 🧾 Invoices – Days Between Issue and Due
sql
SELECT invoice_id, issue_date, due_date,
       DATEDIFF(day, issue_date, due_date) AS days_between
FROM invoices;
Calculates the number of days between issue and due dates.

5. 📚 Courses – Format Start Date
sql
SELECT course_id, name,
       TO_VARCHAR(start_date, 'Month YYYY') AS formatted_date
FROM courses;
Formats course start dates as “Month YYYY”.

6. 🪪 Memberships – Build Full Date
sql
SELECT member_id,
       DATE_FROM_PARTS(start_year, start_month, start_day) AS full_start_date
FROM memberships;
Constructs a full date from year, month, and day parts.

7. 📑 Subscriptions – Extend Renewal by 1 Year
sql
SELECT sub_id, plan,
       DATEADD(year, 1, renewal_date) AS extended_renewal_date
FROM subscriptions;
Extends subscription renewal dates by one year.

8. 🛒 Orders – Days Since Order
sql
SELECT order_id, order_date, CURRENT_DATE AS today_date,
       DATEDIFF(day, order_date, CURRENT_DATE) AS days_since_order
FROM orders;
Calculates how many days have passed since each order.

9. 📖 Trainings – Extract Year
sql
SELECT training_id, topic,
       DATE_PART(year, training_date) AS training_year
FROM trainings;
Extracts the year from training dates.

10. 📝 Blog Posts – Extract Hour and Minute
sql
SELECT post_id, title,
       DATE_PART(hour, published_on) AS hour_published,
       DATE_PART(minute, published_on) AS minute_published
FROM blog_posts;
Extracts hour and minute from blog post timestamps.

11. 🚗 Drivers – Days Until License Expiry
sql
SELECT driver_id, license_expiry,
       DATEDIFF(day, CURRENT_DATE, license_expiry) AS days_left
FROM drivers;
Calculates days left until license expiry.

12. 💬 Messages – Seconds Since Sent
sql
SELECT message_id, sent_timestamp, CURRENT_TIMESTAMP AS current_timestamp,
       DATEDIFF(second, sent_timestamp, CURRENT_TIMESTAMP) AS seconds_since_sent
FROM messages;
Shows how many seconds have passed since each message was sent.

13. 📦 Returns – Restock Date
sql
SELECT return_id, return_date,
       DATEADD(day, 15, return_date) AS restock_date
FROM returns;
Adds 15 days to return date to calculate restock date.

14. 📂 Assignments – Convert String to Date
sql
SELECT assign_id,
       TO_DATE(assigned_on) AS assigned_on_date
FROM assignments;
Converts string values into proper date format.

15. 📅 Meetings – Format Meeting Time
sql
SELECT meeting_id,
       TO_VARCHAR(scheduled_time, 'Month DD, YYYY "at" HH:MI AM') AS formatted_meeting_time
FROM meetings;
Formats meeting time into a readable string like “November 25, 2025 at 09:30 AM”.
