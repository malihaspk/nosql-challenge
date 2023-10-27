# Background
In this Challenge we have been asked to evaluate some of the ratings data in food magazine, **Eat Safe, Love**, in order to help their journalists and food critics decide where to focus future articles. 

# Challenge is divided into Three parts

# Part 1: Database and Jupyter Notebook Set Up

We need to Import the data provided in the **establishments.json** file from  Terminal. Name the database uk_food and the collection establishments with the below command
mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json

The notebook with the name **NoSQL_setup_starter.ipynb** can be found in github repository

Within the notebook, imported the libraries needed: 

PyMongo and Pretty Print (pprint).

 An instance of the Mongo Client has been created.

By Listing the databases in MongoDB, we Confirm that uk_food is listed.

Then , we list the collection(s) in the database to ensure that **establishments** is there.

To check that the data is loaded and working we find and display one document in the establishments collection using find_one and display with pprint.
Finally,Assigned the establishments collection to a variable to prepare the collection for use.


# Part 2: Update the Database

Before making any queries we have been asked to insert a new restaurant **Penang Flavours** to the establishments collection.The notebook with the name **NoSQL_setup_starter.ipynb** can be found in repository with all the related updates.
We find the BusinessTypeID for "Restaurant/Cafe/Canteen" then updated the new restaurant with the BusinessTypeID we found earlier. The magazine is not interested in any establishments in Dover, so we remove any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
Some of the number values are stored as strings, when they should be stored as numbers, so we 
Use update_many to convert latitude and longitude to decimal numbers, and also,
Use update_many to convert RatingValue to integer numbers.


# Part 3: Exploratory Analysis
Eat Safe, Love has specific questions they want you to answer, the notebook  **NoSQL_analysis_starter.ipynb** has been used for this section of the challenge and can be found in git hub repository.

1. We have been asked to find establishments that have a hygiene score equal to 20 that has been done by a *query* and *find* method and returned the value of 41.

2. For establishments in London, those have a RatingValue greater than or equal to 4, we use usethe "$regex" as part of the search for London and "$gte" for RatingValue of 4.

3. We looked for the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours". For this, we  compare the geocode to find the nearest locations and search within 0.01 degree on either side of the latitude and longitude.

4. For the establishments in each Local Authority area that have a hygiene score of 0, we  Sort the results from highest to lowest, and print out the top ten local authority areas by creating a **pipline**.
Finally, a dataframe has been created excatly matching the provided image.


References
https://www.mongodb.com/docs/

