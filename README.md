ETL Project: Mobile Number Validation and Name Uppercasing
Overview
This ETL (Extract, Transform, Load) project showcases a powerful combination of data manipulation using Python. The primary objectives are to validate mobile numbers and convert names to uppercase within a dataset. This can be particularly useful for data cleaning and standardization tasks.

Project Details:

Extract:
The project begins with data extraction from a source, which could be in various formats such as CSV, Excel, or a database.

Transform:
Mobile Number Validation (Python): Python is used to validate mobile numbers within the dataset. It checks for valid formats and ensures consistency.
Name Uppercasing (Python): Python is employed to convert names to uppercase, helping maintain uniformity and consistency.

Load:
After the transformation phase, the cleaned and standardized data can be loaded back into the source or into a new destination, depending on your requirements.

How to Use:
# Python Libraries
import pandas as pd
import re

# Load the source CSV file
source_file = 'input_data.csv'
data = pd.read_csv(source_file)

# Function to validate mobile numbers
def validate_mobile_number(number):
    # Regular expression for a 10-digit Indian mobile number
    pattern = re.compile(r'^[6789]\d{9}$')
    return pattern.match(str(number)) is not None

# Function to convert names to uppercase
def convert_to_uppercase(name):
    return name.upper()

# Validate mobile numbers and convert names to uppercase
data['MobileNumberValid'] = data['MobileNumber'].apply(validate_mobile_number)
data['Name'] = data['Name'].apply(convert_to_uppercase)

# Save the transformed data to a new CSV file
output_file = 'output_data.csv'
data.to_csv(output_file, index=False)

print("ETL process completed successfully!")


Technologies Used:
Python
Data Validation
Data Transformation
Data Cleaning
ETL Process

Contributions:
Contributions are welcome! If you have ideas for improvements or new features, feel free to fork this repository and submit a pull request.

Acknowledgments:
This project was inspired by the need for efficient data cleaning and standardization processes. Thanks to the open-source communities of Python for providing powerful tools for data manipulation.

