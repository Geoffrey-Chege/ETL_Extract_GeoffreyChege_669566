# ETL Extract Lab – Full and Incremental Extraction

## Author
Geoffrey Chege Mwangi  
Student ID: 669566

---

## Project Description
This project demonstrates:
- Full data extraction (loading the entire dataset)
- Incremental data extraction (loading only new records since last extraction)
- Updating the extraction timestamp for the next run

The project is implemented in **Jupyter Notebook** using **VS Code**.

---

## Files in This Repository
- `etl_extract.ipynb` – Jupyter Notebook with all ETL steps
- `custom_data.csv` – Dataset used for extraction (minimum 50 rows)
- `last_extraction.txt` – Tracks the timestamp of the last extraction
- `.gitignore` – Specifies files to exclude from GitHub
- `README.md` – Project documentation

---

## How to Run

### 1. Full Extraction

- Load the entire dataset and display all records.

#### Screenshot: Full Extraction
![Full Extraction Screenshot](Screenshots/Screenshot_(154)_Section1.png)

---

### 2. Incremental Extraction

- Load only new records since the last extraction timestamp.

#### Screenshot: Incremental Extraction
![Incremental Extraction Screenshot](Screenshots/Screenshot_(153)_Section2.png)

---

### 3. Update Last Extraction Timestamp

- Save the current time as the new extraction point for the next run.

#### Screenshot: Timestamp Update
![Timestamp Update Screenshot](Screenshots/Screenshot_(152)_Section3.png)

---

### 4. Transform Full Data
- Apply transformations on the full dataset (cleaning, enrichment, structural, categorization, filtering).
- In Section 4 of the notebook:
  1. Remove duplicates.
  2. Handle any missing values.
  3. Ensure `order_date` is datetime and extract `order_year`, `order_month`, `order_day`.
  4. Add enrichment columns, e.g., `avg_price_per_item`.
  5. Categorize `total_price` into `price_category` (Low/Medium/High).
  6. Drop irrelevant columns if present.
  7. Save result to `transformed_full.csv`.

---

### 5. Transform Incremental Data
- Apply the same transformation logic on the incremental subset.
- In Section 5 of the notebook:
  1. Load incremental extraction results.
  2. Remove duplicates.
  3. Handle missing values.
  4. Ensure datetime and extract parts.
  5. Add enrichment columns (`avg_price_per_item`).
  6. Categorize `total_price` into `price_category`.
  7. Drop irrelevant columns if present.
  8. Save result to `transformed_incremental.csv`.

---

## Data Source
The dataset used in this project was synthetically generated for demonstration purposes.

---

## Tools Used
- Python
- Pandas
- Numpy
- Jupyter Notebook
- VS Code

---

## Git Workflow
1. Initialize the project folder with Git.
2. Add all files.
3. Commit after each completed section.
4. Push the final project to GitHub.

---

## Transformation Details (for reference)

- **Cleaning**: Drop duplicate rows; handle missing values (fill or drop as needed).
- **Structural**: Parse and validate `order_date`; extract year/month/day parts.
- **Enrichment**: Compute `avg_price_per_item = total_price / quantity`.
- **Categorization**: Bin `total_price` into `price_category` ("Low", "Medium", "High").
- **Filtering**: Drop any irrelevant columns (e.g., an `id` column if present).

---

## License
This project is licensed under the MIT License.  
See the [LICENSE](LICENSE) file for details.