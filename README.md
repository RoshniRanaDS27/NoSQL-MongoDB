# Background
<img src="https://www.emugifs.net/wp-content/uploads/2021/09/Homer-Eating-GIF-at-The-Fish-Restaurant-Animation-from-The-Simpson-Cartoon-Episode-Make-Your-MEME-and-Reaction.gif" alt="Homer Eating at The Fish Restaurant GIF">

The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. 
You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

Repo work is devided in to three parts    

- Part 1: Database and Jupyter Notebook Set Up  
- Part 2: Update the Database  
- Part 3: Exploratory Analysis  

# Instructions
# Part 1: Database and Jupyter Notebook Set Up  

1. Used  NoSQL_setup_starter.ipynb for this section of this work.  
2. Imported the data provided in the establishments.json file from my Terminal (#by using MongoDB Codes).  
3. Named the database 'uk_food' and the collection establishments.  
4. Copied the text have used to import data from my Terminal to a markdown cell in jyupiter notebook.  

5. Within that notebook, imported the libraries i needed: PyMongo and Pretty Print (pprint).  
6. Created an instance of the Mongo Client.  

7. Confirmed that have created the database and loaded the data properly:  
#Listed the databases have in MongoDB. Confirmed that uk_food is listed.  
#Listed the collection(s) in the database to ensure that establishments is there.  
#Found and displayed one document in the establishments collection using find_one and display with pprint.

9. Assigned the establishments collection to a variable to prepare the collection for use.

# Details
- Included the "mongoimport" command text, have used to import 'establishments.json' in a markdown cell at the beginning of the Jupyter notebook file.   
- The mongoimport command text correctly dropped any existing 'establishments' collection before importing 'establishments.json' into 'MongoDB'.  
- The database is named 'uk_food' and the collection is named 'establishments'.  
- Correctly imported PyMongo and Pretty Print.   
- An instance of the Mongo Client is created.   
- Listed the databases have in Mongo, which includes 'uk_food'.    
- Listed the collection(s) in the 'uk_food' database, which includes 'establishments' in the output.    
- Used "find_one()" and pprint to display one document in the 'establishments' collection.     
- The 'establishments' collection is assigned to a variable.

# Part 2: Update the Database
Used NoSQL_setup_starter.ipynb for this section of the challenge.  

The magazine editors had some requested modifications for the database before performing any queries or analysis for them. 
Made the following changes to the establishments collection:  

1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet.  
The magazine had asked to include it in the analysis.
(The supplied data for the "Penang Flavours" restaurant was correctly inserted into the establishments collection)    
Added the following information to the database:    

![image](https://github.com/user-attachments/assets/c277da9b-293f-462c-98d6-2b410578a853)

  

2. Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.    
    (A query was performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType)      
3. Updated the new restaurant with the BusinessTypeID found.        
   (The "Penang Flavours" document was updated with the correct value for BusinessTypeID)    
4. The magazine was not interested in any establishments in Dover, 
so checked how many documents contain the Dover Local Authority. 
Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.

5. Some of the number values were stored as strings, when they should be stored as numbers.    
- Used update_many to convert latitude and longitude to decimal numbers.
- Used update_many to convert RatingValue to integer numbers.

# Part 3: Exploratory Analysis    
Eat Safe, Love has specific questions they wanted to answer, which will help them find the locations they wish to visit and avoid.    

- Used "NoSQL_analysis_starter.ipynb" for this section.    
Some notes to be aware of while exploring the dataset:    

- RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5.    
- The higher the value, the better the rating.    

Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating.     
will coerce non-numeric values to nulls during the database setup before converting ratings to integers.    
The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse.    
This means, the higher the value, the worse the establishment is in these areas.    

- Used the following questions to explore the database, and find the answers, so you can provide them to the magazine editors.

# Question 1: Which establishments have a hygiene score equal to 20? 

- A query was performed to find the establishments with a hygiene score of 20.        
- "count_documents()" is used to list the correct number of documents.        
- The first result was printed using pprint.        
- The results are converted to a "Pandas DataFrame" and displays the first 10 rows.     

# Question 2: Which establishments in London have a RatingValue greater than or equal to 4?     

- A query was performed to find the establishments in London with a RatingValue greater than or equal to 4.    
- The query uses the "$regex" operator to locate the London establishments.       
- "count_documents()" was used to list the correct number of documents.    
- The first result was printed using pprint.    
- The results were converted to a Pandas DataFrame and displays the first 10 rows.    

# Question 3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

- A query was performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant.    
- The query also limits the results to establishments with a RatingValue of 5.    
- The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score.    
- The query uses the limit() method in PyMongo to limit the results to 5.    
- All five results were printed using pprint.    
- The results were converted to a Pandas DataFrame and displayed.    

# Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas. 

- An "aggregation pipeline" ws built to include a match query, group, and sort.     
- The match query matches documents with a hygiene score of 0.    
- The group step of the pipeline was grouped on LocalAuthorityName and counts the number of documents.    
- The sort step of the pipeline sorts the count of the documents in descending order.    
- The aggregation pipeline was correctly sent to the aggregate() method.    
- The results from the aggregation query was cast as a list and then saved to a variable.
- The first ten results were printed using pprint.    
- The results were converted to a Pandas DataFrame and displays the first 10 rows.

![image](https://github.com/user-attachments/assets/62316602-b1c8-4833-a17a-edc2596c98b3)

# Deployment Step further took place
