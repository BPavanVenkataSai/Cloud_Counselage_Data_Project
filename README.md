# Student Event Participation Analysis

This project analyzes student participation in various events based on different promotion channels, academic performance, and other factors. The goal is to gain insights into the effectiveness of promotion channels and the relationship between academic metrics and event participation.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Analysis](#analysis)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview
This project aims to:
1. Identify the most effective promotion channels for student event participation.
2. Analyze the relationship between students' GPA, family income, and expected salary.
3. Determine the distribution of students across graduation years.
4. Investigate if leadership skills correlate with higher GPAs or better expected salaries.

## Dataset
The dataset contains information about students' event participation, including:
- First Name
- Email ID
- Quantity (Number of courses completed)
- Events attended
- Attendee Status
- College Name
- Promotion Channel
- Designation
- Year of Graduation
- City
- CGPA
- Experience with Python (Months)
- Family Income
- Expected Salary (Lac)
- Leadership Skills

## Installation
1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/student-event-participation-analysis.git
    ```
2. Navigate to the project directory:
    ```bash
    cd student-event-participation-analysis
    ```
3. Install the required dependencies:
    ```bash
    pip install pandas openpyxl
    ```

## Usage
1. Load the dataset:
    ```python
    import pandas as pd

    # Load your dataset
    data = pd.read_excel('path_to_your_file.xlsx')
    ```

2. Run analyses:
    - Total unique students:
        ```python
        unique_students = data['Email ID'].nunique()
        print(f"Total unique students: {unique_students}")
        ```

    - Average GPA:
        ```python
        average_gpa = data['CGPA'].mean()
        print(f"Average GPA: {average_gpa}")
        ```

    - Distribution across graduation years:
        ```python
        graduation_distribution = data['Year of Graduation'].value_counts()
        print(graduation_distribution)
        ```

    - Average family income:
        ```python
        average_family_income = data['Family Income Numeric'].mean()
        print(f"Average family income: {average_family_income}")
        ```

    - GPA variation among colleges (top 5):
        ```python
        college_gpa = data.groupby('College Name')['CGPA'].mean().reset_index().sort_values(by='CGPA', ascending=False).head(5)
        print(college_gpa)
        ```

    - Average GPA for each city:
        ```python
        city_gpa = data.groupby('City')['CGPA'].mean().reset_index()
        print(city_gpa)
        ```

    - Promotion channel effectiveness:
        ```python
        promotion_channel_counts = data.groupby('How did you come to know about this event?').size().reset_index(name='Student Count').sort_values(by='Student Count', ascending=False)
        print(promotion_channel_counts)
        ```

## Analysis
Various analyses are performed to gain insights into the data:
- Identifying top colleges with the highest participation.
- Examining the correlation between GPA, family income, and expected salary.
- Investigating the impact of leadership skills on GPA and expected salary.

## Results
The results of the analysis include:
- Identification of the most effective promotion channels.
- Average GPA and family income of students.
- Distribution of students across graduation years.
- Relationship between GPA, family income, and expected salary.
- Impact of leadership skills on GPA and expected salary.

## Contributing
Contributions are welcome! Please create a pull request or open an issue to discuss your changes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
