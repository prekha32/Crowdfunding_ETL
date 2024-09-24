# Project-2: Crowdfunding ETL

## Overview
The goal of this project is to analyze food hygiene ratings from the UK Food Standards Agency to aid *Eat Safe, Love* magazine in guiding their articles. This repository contains the necessary tools and datasets to perform ETL processes, updates, and exploratory analysis on the data.

## Project Structure
```
Crowdfunding_ETL/
├── ETL_Mini_Project_RPuthalpet_CMini.ipynb  # Jupyter Notebook for SQL analysis
├── Resources/crowdfunding.xlsx                # Excel file containing crowdfunding data
├── Resources/contacts.xlsx                    # Excel file containing contact information
├── README.md                                   # This README file
```

## Instructions

### Part 1: Database and Jupyter Notebook Setup
1. **Data Import**: Use the `establishments.json` file to create a MongoDB database named `uk_food` and a collection named `establishments`. 
   - Ensure to document the command used for data import in the notebook.

2. **Library Imports**: Import necessary libraries including `PyMongo` and `Pretty Print (pprint)`.

3. **Mongo Client Setup**: Create an instance of the Mongo Client to interact with the MongoDB database.

4. **Database Validation**: 
   - List all databases and ensure `uk_food` is present.
   - Check the collections within `uk_food` to confirm the `establishments` collection exists.
   - Retrieve and display one document from the `establishments` collection using `find_one()`.

5. **Variable Assignment**: Assign the `establishments` collection to a variable for further operations.

### Part 2: Update the Database
1. **Add New Restaurant**: Insert a new halal restaurant in Greenwich that has yet to be rated.

2. **Find BusinessTypeID**: Identify the `BusinessTypeID` for "Restaurant/Cafe/Canteen".

3. **Update Restaurant**: Update the newly added restaurant with the `BusinessTypeID` obtained.

4. **Remove Establishments in Dover**: 
   - Count and delete establishments in the "Dover" Local Authority.
   - Confirm deletion by recounting the documents.

5. **Data Type Conversion**: 
   - Use `update_many` to convert latitude and longitude to decimal numbers.
   - Convert `RatingValue` to integers where applicable.

### Part 3: Exploratory Analysis
Utilize the `NoSQL_analysis_starter.ipynb` notebook to answer specific editorial questions based on the establishments data:

1. **Hygiene Score of 20**: Identify establishments with a hygiene score of 20.
   
2. **London Establishments with High Ratings**: Find establishments in London with a `RatingValue` of 4 or higher. Use regex for matching.

3. **Top Rated Establishments**: Determine the top 5 establishments with a `RatingValue` of 5, sorted by hygiene score and proximity to "Penang Flavours".

4. **Local Authority Hygiene Scores**: Count how many establishments have a hygiene score of 0 in each Local Authority, sorting and displaying the top ten.

### Notes
- **RatingValue**: Ranges from 1-5; higher values signify better ratings.
- **Scores Interpretation**: Non-numeric values like 'Pass' will be treated as `null`. Higher scores for hygiene, structural, and management confidence indicate poorer performance.

## How to Use This Repository
1. Clone the repository to your local machine.
2. Navigate to the `Crowdfunding_ETL/` directory.
3. Open `ETL_Mini_Project_RPuthalpet_CMini.ipynb` and `NoSQL_analysis_starter.ipynb` in Jupyter Notebook or any compatible environment.
4. Follow the instructions outlined in the notebooks to complete the ETL processes and analysis.

## License
This project is licensed under the MIT License. See the LICENSE file for details. 

---

Feel free to contribute to this project by submitting issues or pull requests!
