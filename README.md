# Project-2

Crowdfunding_ETL/
├── **ETL_Mini_Project_RPuthalpet_CMini.ipynb**       # Jupyter Notebook for SQL analysis
├── **Resources/crowdfunding.xlsx**        # This is excel file in Resources folder
├── **Resources/contacts.xlsx**        # This is excel file in Resources folder
├── **README.md**                    # This README file

## Instructions
The UK Food Standards Agency evaluates various establishments across the United Kingdom and assigns them a food hygiene rating. You've been contracted by the editors of a food magazine, *Eat Safe, Love*, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

## Project Structure
## Part 1: Database and Jupyter Notebook Setup

Use **NoSQL_setup_starter.ipynb** for this section of the challenge.

1. Import the data provided in the `establishments.json` file from your Terminal. Name the database `uk_food` and the collection `establishments`. Copy the text you used to import your data from your Terminal to a markdown cell in your notebook.
2. In the notebook, import the necessary libraries: `PyMongo` and `Pretty Print (pprint)`.
3. Create an instance of the Mongo Client.
4. Confirm the database and data import was successful:
    - List the databases in MongoDB and confirm that `uk_food` is listed.
    - List the collection(s) in the `uk_food` database to ensure that `establishments` is present.
    - Find and display one document in the `establishments` collection using `find_one()` and display it with `pprint`.
5. Assign the `establishments` collection to a variable for further use.

## Part 2: Update the Database

Use **NoSQL_setup_starter.ipynb** for this section of the challenge.

The magazine editors have requested the following modifications before performing any queries or analysis:

1. A new halal restaurant has opened in Greenwich but hasn't been rated yet. Add the following information about the restaurant to the database.
2. Find the `BusinessTypeID` for "Restaurant/Cafe/Canteen" and return only the `BusinessTypeID` and `BusinessType` fields.
3. Update the new restaurant with the `BusinessTypeID` found in the previous step.
4. Remove any establishments located in the "Dover" Local Authority:
    - Count how many documents have "Dover" as the Local Authority.
    - Delete these establishments from the database, and re-check the count to ensure deletion.
5. Convert some string-encoded numerical values to their correct data types:
    - Use `update_many` to convert latitude and longitude values to decimal numbers.
    - Use `update_many` to convert `RatingValue` to integers.

## Part 3: Exploratory Analysis

Use **NoSQL_analysis_starter.ipynb** for this section of the challenge.

*Eat Safe, Love* editors have specific questions to guide their content creation, and you will use the establishments data to help them decide where to visit and which places to avoid.

### Notes:
- `RatingValue` refers to the overall rating by the Food Authority and ranges from 1-5. Higher values indicate better ratings.
- Non-numeric values like 'Pass' will be coerced into `null` values during database setup before converting ratings to integers.
- Hygiene, Structural, and ConfidenceInManagement scores work in reverse — higher values indicate worse performance.

### Questions to Answer:
For each question:
- Use `count_documents` to display the number of documents in the result.
- Display the first document in the results using `pprint`.
- Convert the results into a Pandas DataFrame, display the number of rows in the DataFrame, and show the first 10 rows.

1. **Which establishments have a hygiene score of 20?**
2. **Which establishments in London have a `RatingValue` of 4 or higher?**  
   - Hint: Use `$regex` to search for establishments in London (the Local Authority name might be longer than just "London").
3. **What are the top 5 establishments with a `RatingValue` of 5, sorted by the lowest hygiene score, nearest to the new restaurant "Penang Flavours"?**
   - Hint: Use geocode data to find the nearest locations. Search within 0.01 degree on either side of the latitude and longitude.
4. **How many establishments in each Local Authority have a hygiene score of 0?**  
   - Sort the results from highest to lowest and print the top ten Local Authorities.
   - Hint: Use the aggregation method to perform this task.

