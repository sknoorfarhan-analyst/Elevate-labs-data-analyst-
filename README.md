# Elevate-labs-data-analyst-
📋 Task 1: Data Preprocessing & Cleaning SummaryDataset Name: Marketing Campaign DataTotal Records Processed: 2,240 rows | 29 columns
Objective: Clean raw campaign data by resolving layout structural errors, handling missing variables, standardizing text inputs, and aligning dates/data types.
Key Modifications:
LogColumn Splitting & Layout Realignment: The raw file used a tab-delimited (\t) structural arrangement that squeezed data into a single cluster. This was separated cleanly into 29 distinct functional columns.
Column Header Normalization: All 29 column headers were reformatted from mixed CamelCase/PascalCase to clean, uniform database-ready lowercase formatting (e.g., Year_Birth $\rightarrow$ year_birth).
Missing Value Resolution (.isnull()): Identified 24 null rows inside the income column. To preserve customer historical metrics and transaction continuity, the blanks were populated using the statistical median income of $51,381.50.
Deduplication (.drop_duplicates()): Scanned the unique identifier column (id). No structural duplicate rows were found across the 2,240 unique records, ensuring structural data integrity.
Text Categorization Standardizing: Inspected text fields for consistency. Found irregular responses in marital_status. Irregular edge cases (Alone, Absurd, and YOLO) were standardized cleanly into Single to enable clean statistical grouping.
Data Type Correction & Date Conversions: * Transformed the text-based enrollment column dt_customer into a unified datetime64 format (DD-MM-YYYY).
Validated numeric variables (id, year_birth, product columns) ensuring they are recognized strictly as numerical values (int64 / float64) rather than strings to protect future calculations.
