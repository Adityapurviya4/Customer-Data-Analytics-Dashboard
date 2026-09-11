# Customer-Data-Analytics-Dashboard
Designed a normalized SQL schema for customer accounts, orders, and support interactions, building a JavaScript-powered web app to query and visualize data.  Debugged and resolved authentication and session management workflows using server logs and browser DevTools.

**1. What the Project Does**

* **Centralized Storage:** Keeps track of three main things: who your customers are, what they are buying, and what problems or support tickets they are facing.
* **Visual Insights:** Turns raw database numbers into interactive dashboards and charts so stakeholders can instantly see trends (e.g., top-selling products or common support complaints).
* **Secure Access:** Includes a login system so only authorized users can view the data.

**2. How the SQL Database Works**
The backend uses a **normalized SQL schema**. "Normalized" simply means organizing data into separate, logical tables to avoid repetition and keep things clean.

* **Customers Table:** Stores individual user details (`customer_id`, `name`, `email`, `signup_date`).
* **Orders Table:** Stores purchase details (`order_id`, `customer_id`, `product_name`, `amount`, `order_date`). The `customer_id` acts as a bridge (foreign key) linking the order back to the specific buyer.
* **Support Interactions Table:** Stores customer service records (`ticket_id`, `customer_id`, `issue_type`, `status` like open/resolved, `date`).
* *Why it matters:* If a customer updates their email, you only change it in one place (`Customers` table), and it automatically updates everywhere.

**3. How the JavaScript & Web App Works**

* **The Backend (Node.js):** Acts as the brain. When a user opens the dashboard, Node.js sends SQL queries to the database (e.g., pulling total sales or active support tickets), processes the results, and sends them to the frontend.
* **The Frontend (HTML/CSS/JS):** Receives that data from the backend and displays it inside clean cards, tables, or charts using JavaScript.

**4. Authentication & Debugging Workflow**

* **Managing Sessions:** The app tracks whether a user is logged in using session cookies or tokens. When a user logs in, the server remembers them as they navigate between pages.
* **Debugging Issues:**
* If a button breaks or data doesn't load, you check **Browser DevTools** (looking at the *Network* tab to see if the API request failed or returned an error code).
* If the database query fails, you check the **Server Logs** in your terminal to see the exact SQL syntax error or Node.js crash report.



**5. Presenting to a Non-Technical Audience**

* Instead of showing raw data tables or code lines like `SELECT COUNT(*) FROM support WHERE status='open'`, you translate the findings into a plain-language story.
* *Example:* "Over the last month, our support volume spiked by 20%, with billing issues making up the majority of complaints—meaning we should update our checkout documentation."
