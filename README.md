Ledger Data Repository
This repository contains a collection of CSV files extracted from a larger ledger spreadsheet. It's designed to provide a structured and easily accessible record of financial or transactional data, broken down by individual participants and a general overview.

Table of Contents
Project Overview

File Structure

Data Schema (Template)

Screenshots

Usage

Contributing

License

Contact

Project Overview
This project serves as a centralized place for maintaining and sharing ledger data. Each CSV file represents a specific aspect of the ledger: a general overview, a template for new entries, and individual records for various people. This setup allows for clear separation of concerns and easier data management.

The primary goal is to:

Organize ledger entries in a consistent format.

Provide individual breakdowns of transactions.

Facilitate easy access and analysis of ledger data.

File Structure
The repository is organized with a flat structure, where all CSV files are located in the root directory. Each file is named to clearly indicate its content.

### Sheet Naming Convention

When working with the `Ledger.xlsx` file, please adhere to the following naming convention for the sheets:

1.  **Index Sheet**: There should be an "Index" sheet that lists all the individuals or companies for whom a ledger sheet exists.
2.  **Individual/Company Sheets**: Each subsequent sheet should be named after the person or company it represents. This name must exactly match an entry in the "Index" sheet.

For example, if you have a person named "John Doe" listed in the "Index" sheet, their corresponding ledger sheet should be named "John Doe".

*   **Ledger.xlsx - Name.csv**: This file likely contains a list of names or categories associated with the ledger, possibly mapping IDs to human-readable names.
*   **Ledger.xlsx - Template.csv**: This is the crucial template file that defines the column headers and expected data types for all individual ledger entries. It serves as a guide for anyone creating or modifying ledger data.

Ledger.xlsx - Person 1.csv to Ledger.xlsx - Person 15.csv: These files contain the individual ledger entries for each person (Person 1 through Person 15). Each file adheres to the structure defined in Ledger.xlsx - Template.csv.

Data Schema (Template)
The Ledger.xlsx - Template.csv file defines the structure for all individual ledger entries. It's essential to follow this template when adding new data. While the exact columns are defined in the file itself, common ledger fields often include:

Screenshots
To help visualize the project, here are some key screenshots:

1. Ledger Template Overview
This screenshot shows the Ledger.xlsx - Template.csv file, illustrating the expected column headers and structure for all ledger entries.

![Ledger Template Overview](assets/template.png)

2. Individual Ledger Entries Example
This screenshot displays a sample of data from one of the Ledger.xlsx - Person X.csv files, demonstrating how individual transactions are recorded.

![Individual Ledger Entries Example](assets/sample.png)

3. Data Loading in Python
This screenshot captures the Python example from the "Usage" section, showing the code and its output in a terminal or code editor, verifying basic data loading and processing.

![Data Loading in Python](assets/index.png)

Usage
You can use these CSV files for various purposes:

Viewing Data: Open any CSV file in a spreadsheet program (like Microsoft Excel, Google Sheets, LibreOffice Calc) or a text editor to view the raw data. Refer to the screenshots above for examples.

Data Analysis: Import the CSV files into data analysis tools (e.g., Python with Pandas, R, SQL databases) to perform calculations, generate reports, or visualize trends.

Integration: Use these files as a data source for other applications or scripts that require ledger information.

Example: Basic Data Loading (Python)
import pandas as pd

# Load the template
template_df = pd.read_csv('Ledger.xlsx - Template.csv')
print("Template Columns:", template_df.columns.tolist())

# Load a person's ledger
person1_df = pd.read_csv('Ledger.xlsx - Person 1.csv')
print("\nPerson 1 Data (first 5 rows):")
print(person1_df.head())

# Calculate total expenses for Person 1 (example, assuming 'Type' and 'Amount' columns)
if 'Type' in person1_df.columns and 'Amount' in person1_df.columns:
    total_expenses_person1 = person1_df[person1_df['Type'] == 'Expense']['Amount'].sum()
    print(f"\nTotal Expenses for Person 1: ${total_expenses_person1:.2f}")

Contributing
If you wish to contribute to this ledger data, please follow these guidelines:

Maintain Consistency: Always adhere to the column structure defined in Ledger.xlsx - Template.csv when adding or modifying data in the Person X.csv files.

Data Integrity: Ensure the accuracy of all entries.

New Person Files: If adding a new person's ledger, create a new CSV file named Ledger.xlsx - Person [Next Number].csv and ensure it follows the template.

Pull Requests: For any significant changes or additions, please submit a pull request with a clear description of your modifications.

License
This project is licensed under the MIT License - see the LICENSE file for details.
(Note: You'll need to create a LICENSE file in your repository if you don't have one already, containing the text of the MIT License.)

Contact
If you have any questions, suggestions, or issues, please feel free to open an issue in this repository or contact the repository maintainer.