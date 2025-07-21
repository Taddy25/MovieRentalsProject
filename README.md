#  Movie Rental Analytics Project

This is a simple data analysis project using SQLITE3 and Python (Pandas) to simulate a movie rental business scenario. 
The aim is to demonstrate querying, joining, and analysing relational data using SQL and Python — skills relevant for entry-level data roles.

---

## Tools Used

- **SQLite** (via SQLite Studio and Google Colab)
- **Google Colab** for running Python
- **Pandas** for data manipulation

---

# Project Goals

- Simulate a basic movie rental database with customers, movies, and rentals.
- Perform queries and updates using SQL.
- Use Python and Pandas to analyze rental activity:
  - Who returned movies on time or late?
  - Which customers haven’t returned their movies?
  - How many days late were they?

---

# Database structure

Three tables:
- `customers (id, name, email)`
- `movies (id, title, genre)`
- `rentals (id, customer_id, movie_id, rental_date, due_date, return_date)`

Foreign keys link `rentals` to `customers` and `movies`.

---

# Key Insights

- Days late are calculated using `return_date - due_date`.
- If `return_date` is `NULL`, the rental is still out.
- A `return_status` column classifies each rental:
  - Returned on time
  - Returned late
  - Not returned

---

# Example Output

| name              | title            | rental_date | due_date   | return_date | return_status     | days_late |
|------------------ |------------------|-------------|------------|-------------|-------------------|-----------|
| Alice Smith       | Inception        | 2025-07-01  | 2025-07-08 | 2025-07-07  | Returned on time  | -1        |
| Dave Jones        | The Godfather    | 2025-07-02  | 2025-07-09 | 2025-07-11  | Returned late     | 2         |
| Liam Williams     | Toy Story        | 2025-07-03  | 2025-07-10 | NaT         | Not returned      | 0         |
| Taddy Muroyiwa    | Forrest Gump     | 2025-07-04  | 2025-07-11 | NaT         | Not returned      | 0         |
| Steven Spielberg  | The Dark Knight  | 2025-07-05  | 2025-07-12 | NaT         | Not returned      | 0         |

