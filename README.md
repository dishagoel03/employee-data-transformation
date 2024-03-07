# employee-data-transformation
Objective: Transform current employee data from a columnar format into a historical, row-based versioning format suitable for database storage using Python.
Task Overview: The task is to convert an input CSV file containing employee data into a structured format representing historical records of employee compensation, engagement, and performance reviews using Python. The new format requires transforming columnar data into a row-based historical versioning system for insertion into our data warehouse.
## Methodology

The transformation process involves the following steps:

1. **Read Input CSV File:** The Python script reads the input CSV file containing employee data using the Pandas library.

2. **Data Transformation:** The script iterates through each row of the input data and transforms the columnar data related to compensation, engagement, and review into a row-based format. It derives effective dates and end dates for each historical record, ensuring no overlap and handling missing data by inheriting values from the most recent past record for the same employee.

3. **Output CSV File:** After transformation, the script writes the transformed data into a new CSV file formatted for historical data analysis.

## Assumptions

- If data for a range is missing, the script assumes that the missing values should be inherited from the most recent past record for the same employee.
- The script assumes that the "Variable Pay" and "Tenure in Org" fields are not provided in the input data, so they are set to 0 in the output.
