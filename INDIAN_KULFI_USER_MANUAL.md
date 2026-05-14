# Indian Kulfi App - Complete User Manual

## 1. Introduction

The Indian Kulfi App is a Django-based operations system for:
- Product management
- Inventory movement tracking
- Daily sales entry and review
- Operations expense and income tracking
- Profit, income statement, and stock reporting
- User access control

The app is designed for day-to-day store operations with date-based data entry and printable/exportable reports.

---

## 2. User Roles and Access Control

### 2.1 Admin Users
Admin users (staff users) can access all modules:
- Dashboard
- Products
- Inventory Management
- Kulfi Sales
- Kulfi Operations
- Reports
- User Management

### 2.2 Sales Users (Non-Admin)
Sales users can access only the Sales module:
- Daily Sales Sheet (with Stock Taken and Balance Count features)

Other modules are hidden in the sidebar and blocked at URL level.

### 2.3 Login Redirect Behavior
- Admin login redirects to Dashboard.
- Non-admin login redirects to Daily Sales Sheet.

---

## 3. Navigation Overview

### 3.1 Main Sidebar (Admin)
- Dashboard
- Products
  - View All Products
  - Add New Product
  - Trash
- Inventory Management
  - Quick Entry
  - View Stock
  - Stock History
  - New Stock Order
- Kulfi Sales
  - Sales Stock Taken
  - Daily Sales Sheet
  - View Sales
  - Sales History
- Kulfi Operations
  - Quick Operations Entry
  - Quick Income Entry
  - View Expenses
- Reports
  - Daily Report
  - Weekly Report
  - Profit Report
  - Income Statement
  - Stock Report

### 3.2 Main Sidebar (Sales User)
- Kulfi Sales only
  - Daily Sales Sheet

---

## 4. Module-by-Module Usage

## 4.1 Authentication

### Login
1. Open app URL.
2. Enter username and password.
3. Click login.

### Logout
1. Click Logout from the top bar.

---

## 4.2 Dashboard (Admin)

Shows today-level snapshots in five aligned metric cards:
- Today's Sales (transaction count)
- Total Stock (units in inventory)
- Total Revenue for today
- Operation Cost for today
- Net Profit (after operations)

Also includes:
- Low stock alerts
- 7-Day Sales Trend chart (sales count and revenue)
- Top Products table (by sales count)
- Quick Actions: Quick Sales Entry, Quick Operations Entry, Quick Entry, View Inventory

Use this page for a quick health check at start and end of day.

---

## 4.3 Products (Admin)

### Add New Product
1. Go to Products -> Add New Product.
2. Enter product details:
   - Name
   - SKU
   - Category
   - Cost price
   - Selling price
   - Reorder level
3. Save.

### View and Edit Products
1. Go to Products -> View All Products.
2. Use edit action to modify product details.

### Delete and Restore
- Soft delete moves product to Trash.
- Restore from Trash if needed.
- Permanent delete is available from Trash.

---

## 4.4 Inventory Management (Admin)

### Quick Entry
Use for fast stock updates with multiple rows.

Each row supports:
- Product
- Movement type: IN, OUT, ADJUSTMENT
- Quantity
- Quantity unit: NOS or PACK
- Cost price
- Movement date

Important behavior:
- PACK is converted to units (1 pack = 6 units).
- Manufacturer-specific pricing support exists in quick inventory flow.
- Backdated entries are supported via movement date.

### View Stock
Use filters and sorting to review live inventory state.

Filters available:
- Search (name, SKU, category)
- Category
- Stock status (low stock / in stock)
- Movement type
- As-of date (for historical stock)
- Sorting by name, SKU, stock, cost, selling price
- Pagination (per page)

Exports:
- Print HTML
- PDF
- Excel
- CSV

### Stock History
Review inventory movement history by date.

### New Stock Order
Create stock purchase orders with manufacturer and item details.

---

## 4.5 Kulfi Sales

## Sales Stock Taken (Admin + Sales)
Record the stock taken by a salesperson at the start of their shift.
This provides tracking of how much stock each salesperson takes and allows balance count calculation.

## Daily Sales Sheet (Admin + Sales)
Use this for daily and backdated sales recording.

General flow:
1. Open Kulfi Sales -> Daily Sales Sheet.
2. Choose date.
3. Enter product lines and quantity.
4. Submit.

Admin view:
- Shows Avg Unit Price, Combined Stock, Sales Count, and Estimated Total columns.
- Summary: Total Items Sold, Total Sales Count, Total Selling Price.

Sales user view:
- Shows Combined Stock, Stock Taken Count, Sales Count, Balance Count, and Estimated Total columns.
- Summary: Total Stock Taken, Total Items Sold, Total Sales Count, Total Balance Count, Total Selling Price.
- Buttons: Save Stock Taken, Save Sales Count, Record Sales.

Notes:
- System validates stock and shows warnings for failed rows.
- Multiple product rows can be submitted together.
- Stock is reduced automatically when sale is saved.
- If Sales Count is left empty and Record Sales is clicked, saved Stock Taken counts are treated as sold.

## View Sales by Date (Admin + Sales)
This screen supports filtering and reporting.

Filters available:
- Date
- Sales person (user who recorded the sale)

How to use salesperson filter:
1. Select date.
2. Select Sales Person (or keep All Sales Persons).
3. Click View Sales.

What you get:
- Filtered sales table
- Totals (count, revenue, quantity)
- Print and export actions

Print/Export:
- Print HTML
- Download PDF
- Download Excel

The salesperson filter is carried into print/export output.

## Sales History (Admin + Sales)
Use date range and search-style review for past sales records.

### Edit/Delete Sales
- Admin only.
- Non-admin users cannot edit or delete sales records.

---

## 4.6 Kulfi Operations (Admin)

## Quick Operations Entry
Use this for daily operating expenses.

Fields:
- Date
- Details of Operation
- Amount

Daily summary includes:
- Sales amount for selected date
- Other Income for selected date
- Operation cost for selected date
- Net after operations

Navigation:
- Previous/next day buttons for quick date navigation
- Date picker for jump to specific date
- Link to Quick Income Entry

### Edit/Delete in Daily Operations Sheet
Actions are available in each row:
- Edit icon: loads row into form for update
- Delete icon: removes row after confirmation

## Quick Income Entry
Record non-sales income (e.g., deposits, other revenue).

Fields:
- Date
- Details
- Amount

## View Expenses
Use this to review expense entries with date-range filtering.

Filters:
- Start date
- End date

Output:
- Matching operations entries
- Total operation cost for selected range

Exports:
- Print HTML
- PDF
- Excel
- CSV

---

## 4.7 Reports (Admin)

## Reports Dashboard
Central entry point for report modules. Shows quick stats:
- Today's Sales (transactions)
- Today's Revenue
- This Week's Sales
- This Week's Revenue

Report cards link to:
- Daily Report
- Weekly Report
- Profit Report
- Income Statement
- Stock Report
- Sales History

## Daily Report
Shows selected day metrics such as:
- Transactions
- Revenue
- Cost
- Profit
- Operations cost
- Net profit

Print/export options are available (HTML, PDF, Excel).

## Weekly Report
Shows week-range performance with aggregates and export options (HTML, PDF, Excel).

## Profit Report
Shows profitability analysis by date range and product insights.
Print/export options (HTML, PDF, Excel).

## Income Statement
Profit and loss statement for a selected period.
Shows revenue, cost of goods, gross profit, operating expenses, other income, and net profit.
Print/export options (HTML, PDF, Excel).

## Stock Report
Tracks stock-in entries for Indian Kulfi and Kulfi Corner.

Modes:
- General report
- Detailed report

Summary includes:
- Total entries
- Total quantity in
- Indian Kulfi quantity
- Kulfi Corner quantity
- Total purchase cost

Exports:
- Print HTML
- PDF
- Excel

---

## 4.8 User Management (Admin)

Available actions:
- View users
- Add user
- Edit user
- Delete user

Use this section to maintain admin and sales users.

Recommended policy:
- Keep minimum number of admin accounts.
- Use non-admin accounts for day-to-day sales entry.

---

## 5. Daily Operating SOP

### Morning
1. Admin checks Dashboard.
2. Admin records opening stock changes if needed in Inventory Quick Entry.

### During Day
1. Sales user records stock taken via Daily Sales Sheet (Save Stock Taken).
2. Sales user records sales via Daily Sales Sheet (Record Sales).
3. Admin records operation expenses in Quick Operations Entry.
4. Admin records any other income in Quick Income Entry.

### End of Day
1. Open View Sales and filter by date (and optionally salesperson).
2. Verify sales totals.
3. Open Daily Report and confirm net profit.
4. Export daily report (PDF/Excel) for record keeping.

---

## 6. Common Tasks

### Task: See sales by one salesperson
1. Go to View Sales.
2. Select date.
3. Select Sales Person.
4. Click View Sales.

### Task: Correct an operations expense entry
1. Go to Quick Operations Entry.
2. Pick date.
3. Click edit icon on entry row.
4. Update values and save.

### Task: Delete wrong operations entry
1. Go to Quick Operations Entry.
2. Click delete icon in row.
3. Confirm deletion.

### Task: Print stock report with totals
1. Go to Stock Report.
2. Select date range and mode.
3. Click Print and choose HTML/PDF/Excel.

### Task: Create a new stock order
1. Go to Inventory Management -> New Stock Order.
2. Select manufacturer and date.
3. Add items with lot and quantity.
4. Save order.

### Task: Record non-sales income
1. Go to Kulfi Operations -> Quick Income Entry.
2. Enter date, details, and amount.
3. Save.

### Task: View Income Statement
1. Go to Reports -> Income Statement.
2. Select date range.
3. View or export the profit and loss statement.

---

## 7. Troubleshooting Guide

### 7.1 Error: no such table
Typical message example:
- no such table: inventory_operationsexpense

Cause:
- Pending migrations not applied.

Fix:
1. Activate virtual environment.
2. Run migrations:
   - python manage.py migrate
3. Reopen the page.

### 7.2 Sales row not saved
Possible reasons:
- Quantity invalid
- Quantity more than stock
- Product mismatch

Fix:
- Check warning messages displayed after submit.
- Correct rows and resubmit.

### 7.3 Non-admin cannot open module
This is expected behavior.
- Non-admin users are restricted to Sales module only.

### 7.4 Print output not matching on-screen filter
Ensure the filter is set before clicking print/export.
- View Sales print links now carry date and salesperson filter.

---

## 8. Data Backup and Recovery

### SQLite Backup
Create periodic backups of database file:
- db.sqlite3

Recommended:
- End-of-day copy
- Weekly archive copy with date-stamped filename

### Media/Logo Backup
Also back up the media directory to preserve uploaded branding assets.

---

## 9. Security and Best Practices

- Use unique passwords per user.
- Keep admin users limited.
- Disable or delete inactive accounts.
- Avoid sharing accounts between staff.
- Review sales and operations entries daily.

---

## 10. Quick Reference

### Core Sales Pages
- Daily Sales Sheet
- View Sales
- Sales History

### Core Admin Pages
- Dashboard
- Inventory Quick Entry
- New Stock Order
- Quick Operations Entry
- Quick Income Entry
- View Expenses
- Daily/Weekly/Profit/Income Statement/Stock Reports
- User Management

---

## 11. Support Checklist for Admin

When a user reports an issue, collect:
1. Username and role (admin/non-admin)
2. Exact page and date filter used
3. Error text screenshot (if any)
4. Whether issue appears in print/export too
5. Whether migration is up-to-date

---

## 12. Version Notes (Current Behavior)

Current manual reflects these key implemented behaviors:
- Operations module with Date, Details, Amount
- Operation expenses included in daily net profit
- Quick Operations daily sheet supports edit/delete actions with day navigation
- Quick Income Entry for non-sales revenue
- View Expenses is available with date range filter and full export (HTML/PDF/Excel/CSV)
- Income Statement report for profit and loss analysis
- New Stock Order for creating purchase orders
- Sales Stock Taken for tracking stock distributed to salespersons
- Daily Sales Sheet with role-based views (admin vs sales user)
- Balance Count tracking for sales users (Stock Taken minus Sales Count)
- Role-based restrictions enforce sales-only access for non-admin users
- View Sales supports salesperson-level filtering and filtered print/export
- Reports Dashboard with quick stats and links to all report modules
- Dashboard with 5 aligned metric cards and 7-day sales trend chart
