# Task Automation Script — Email Extractor

A simple Python script that automates a small, repetitive real-life task: extracting all email addresses from a `.txt` file and saving them to a separate output file.

## Overview

This project demonstrates basic task automation using Python. Instead of manually scanning through a text file to find email addresses, the script uses regular expressions to automatically detect and extract every valid email address, removes duplicates, and saves the results to a new file — all with minimal user input.

## Features

- Reads any `.txt` file provided by the user
- Validates that the input file exists before processing
- Uses regular expressions (`re`) to accurately detect email addresses
- Automatically removes duplicate email addresses
- Sorts extracted emails alphabetically
- Saves the results to a user-named output file
- Displays the extracted emails directly in the console

## Key Concepts Used

- **os** — checks whether the input file exists before attempting to read it
- **re (Regular Expressions)** — searches the text for patterns matching valid email addresses
- **File Handling** — reads the input `.txt` file and writes extracted emails to an output file
- **Set/List Operations** — removes duplicate matches and sorts the final results

## How to Run

1. Make sure Python 3 is installed on your machine.
2. Save the script as `email_extractor.py`.
3. Open a terminal in the folder containing the script.
4. Run the following command:

   ```
   python email_extractor.py
   ```

## How to Use

1. When prompted, enter the path to the `.txt` file you want to scan (e.g., `sample_input.txt`).
2. Enter a name for the output file (e.g., `emails.txt`), or press Enter to use the default name.
3. The script will scan the file, extract all unique email addresses, and:
   - Save them to the output file
   - Print them to the console

## Example Session

**Input file (`sample_input.txt`):**
```
Hi team,

Please reach out to john.doe@example.com or sarah_smith99@company.org for questions
about the project. You can also cc our support team at support@helpdesk.io.

For billing issues, contact billing@finance-team.co.uk.
Note: john.doe@example.com is out of office until Friday, so use jane.doe@example.com instead.

Thanks,
Admin Team
```

**Console output:**
```
Email Extractor

Enter the path to the input .txt file: sample_input.txt
Enter the name for the output file (e.g., emails.txt): emails.txt
Found 5 unique email address(es).
Saved to 'emails.txt'.

Extracted emails:
  billing@finance-team.co.uk
  jane.doe@example.com
  john.doe@example.com
  sarah_smith99@company.org
  support@helpdesk.io
```

**Output file (`emails.txt`):**
```
billing@finance-team.co.uk
jane.doe@example.com
john.doe@example.com
sarah_smith99@company.org
support@helpdesk.io
```

## Notes

- Duplicate email addresses in the input file are automatically removed in the output.
- The script does not verify whether an email address actually exists or is deliverable — it only checks that the text matches a valid email format.
- If no email addresses are found, the script will notify the user and skip creating an output file.
- No internet connection or external libraries are required — everything runs locally.

## Possible Future Improvements

- Support scanning multiple files or an entire folder at once
- Add support for `.csv` or `.docx` input files
- Extract additional data types, such as phone numbers or URLs
- Add command-line arguments instead of interactive prompts
- Generate a summary report of how many emails were found per file
