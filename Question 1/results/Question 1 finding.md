report = '''# Assignment 2 – Results and Findings

## Question 1 – Used Car Dataset (train.csv)

### Overall goal
Clean the used car dataset, fix missing and messy values, and create a new feature that can be used later for modeling or analysis.

---

### 1. Fix missing values

**What I did**
- I checked all columns to see how many missing values were present.
- I selected numeric columns and filled their missing values using the median.
- I selected categorical columns and replaced missing values with the mode.
- I verified that the dataset had no more missing or empty cells.

**Interpretation**
- This step prevents errors because models cannot work with missing data.
- Using the median preserves the original pattern without being affected by outliers.
- Filling categories with the most common value keeps the data consistent.
- The dataset becomes complete, clean, and reliable for the next steps.

---

### 2. Removing Units from Columns

**What I did**

- I created a function to extract only numbers from strings with units.
- I applied this function to mileage, engine, power, and new price columns.=
- I converted all extracted values into numeric format.
- I checked updated columns to ensure no unit text remained.

**Interpretation**

- Removing units makes these features ready for calculations and modeling.
- This avoids errors that happen when numbers and text are mixed.
- Models understand pure numbers better than strings.
- This step improves accuracy because all values become consistent.


---

### 3. Encoding categorical variables

**What I did**

- I identified all the categorical (object-type) columns in the dataset.
- I converted these columns into dummy variables using get_dummies().
- I used ***drop_first=True*** to avoid creating redundant columns.
- I replaced the original categorical columns with the new encoded ones.

**Interpretation**

- Machine-learning algorithms need numbers, not text labels.
- One-hot encoding helps the model understand category differences.
- Dropping the first dummy prevents multicollinearity issues.
- This step prepares the data for cleaner and more stable predictions.

---

### 4. Creating a new feature (car age) from the year

**What I did**

- I calculated the current year using Python’s date function.
- I checked whether the dataset had a “Year” column.
- I subtracted the manufacturing year from the current year to get Car_Age.
- I added Car_Age as a new column in the dataset.

**Interpretation**

- Car age is more meaningful than the raw manufacturing year.
- It helps models understand depreciation and value drop over time.
- This feature strengthens prediction accuracy for price-related outputs.
- Adding this new feature increases the dataset’s overall information quality.
---

### 5. Filtering, renaming, and summarizing with a new feature

**What I did**
- I selected specific columns to explore the data more closely.
- I filtered rows based on values above the median of the first column.
- I renamed the first column and created a new transformed feature.
- I sorted the dataset and generated group summaries using the last column.

**Interpretation**
- These actions help focus on relevant and meaningful parts of the dataset.
- Filtering highlights patterns among higher or lower values.
- Renaming and creating new features improves clarity and analysis depth.
- Group summaries reveal average trends and support decision-making.

---

