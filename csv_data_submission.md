# CSV Data Submission Guide

## Introduction
This document provides guidelines for software developers on how to prepare and submit client data to IncludeHealth. Please ensure all data conforms to the structure and standards outlined below. The data includes Personal Health Information (PHI) and is protected under a Business Associate Agreement (BAA) with IncludeHealth.

## Data Format
All client data must be submitted in a CSV file with the following required columns:

- **FirstName**: First name of the patient. (String)
- **LastName**: Last name of the patient. (String)
- **DateOfBirth**: Date of birth of the patient, formatted as YYYY-MM-DD. (Date)
- **Email**: Email address of the patient. (String)
- **PhoneNumber**: Contact phone number of the patient, including only the numeric characters, with the +1 US country code assumed. (Numeric)
- **PatientId**: A unique identifier for the patient. (String or Numeric)
- **PlanId**: A unique identifier for the patient's plan, provided by IncludeHealth. This field is an enumeration related to the required assessment for the patient. If a match cannot be made, the patient will not be added, and this will be noted in a "failed results" CSV file. (String)
- **StartDate**: Start date for the plan, formatted as YYYY-MM-DD. (Date)
- **Group**: Group or category the patient belongs to. (String)
- **TimezoneId**: Timezone identifier, consistent with the TZ database format. For a complete list of acceptable timezone identifiers, please refer to the [List of TZ Database Time Zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) on Wikipedia. (String)

See the sample template for examples of properly formatted [CSV example file](TemplateCSVSubmission-Example.csv)

## Data Submission Requirements
- **All fields are required**: Each column must be populated with valid data; otherwise, the record will be rejected.
- **Date Format**: All dates must follow the YYYY-MM-DD format.
- **File Format**: Data must be submitted in CSV format only.
- **Phone Number Format**: Phone numbers must contain only numeric characters. It is assumed that all numbers are prefixed with the +1 US country code.

## Security and Compliance
- **Handling PHI**: As the data includes PHI, all handling and transmission must comply with the stipulated BAA terms.
- **Data Transmission**: Upload all CSV files to the IncludeHealth sFTP server. Credentials and access details will be provided separately.

## Error Handling
- **Failed Results**: If a patient's data cannot be matched to a provided PlanId, it will be flagged in a "failed results" CSV file which will also be available on the sFTP server.

## Support
For any issues or questions regarding data submission or format, please contact our technical support team at support@includehealth.com.
