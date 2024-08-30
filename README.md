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
![image](https://github.com/user-attachments/assets/38d0d4c1-26f8-40d5-ba41-8a57b1af510a)
![image](https://github.com/user-attachments/assets/ed2fe7a4-4817-42b7-aca4-53c13f436b4a)
![image](https://github.com/user-attachments/assets/f2010c11-89cc-43f2-9ad8-ae2c2830d017)
![image](https://github.com/user-attachments/assets/f9b1e55c-b8e9-43d3-a516-b6de34b03535)
![image](https://github.com/user-attachments/assets/22df6acb-e9de-4e34-9492-7e74b887150d)
![image](https://github.com/user-attachments/assets/da23e93c-7977-4b96-8a3e-231512e7f337)
![image](https://github.com/user-attachments/assets/8eb22459-67f2-4a6b-a575-2781e9856727)
![image](https://github.com/user-attachments/assets/1ff106d9-8640-43b4-9873-6684819045a1)
![image](https://github.com/user-attachments/assets/fd2de6be-eba5-4211-9d6f-74fa4542826e)
![image](https://github.com/user-attachments/assets/c8e67050-3b70-41b9-8151-297be97c755e)

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

8. Assigned the establishments collection to a variable to prepare the collection for use.

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
![image](https://github.com/user-attachments/assets/07985c30-50d8-49a2-ae38-728f4c67377c)

1. An exciting new halal restaurant just opened in Greenwich, but hasn't been rated yet.  
The magazine had asked to include it in the analysis.
(The supplied data for the "Penang Flavours" restaurant was correctly inserted into the establishments collection)    
Added the following information to the database:    
![image](https://github.com/user-attachments/assets/d9696e5c-221e-4211-8fcf-decd7ca6e79d)
![image](https://github.com/user-attachments/assets/14386640-cb1e-4e32-b867-d1f266f99f53)
      
2. Updated the new restaurant with the BusinessTypeID found.        
   (The "Penang Flavours" document was updated with the correct value for BusinessTypeID)
![image](https://github.com/user-attachments/assets/ed720f4c-82d6-4307-9aee-17663318acd6)
![image](https://github.com/user-attachments/assets/cfa2a353-f608-4679-b17c-a8b39534e0cf)
![image](https://github.com/user-attachments/assets/5bcc827b-7dd7-4b9d-9afc-23f5716ac3f5)

3. Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.    
    (A query was performed to find the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType)  
![image](https://github.com/user-attachments/assets/cfa5a696-de62-4ca2-92a5-56a27202b9aa)
![image](https://github.com/user-attachments/assets/728ce2b4-ed4f-433b-bf63-dd3c21586fa0)
![image](https://github.com/user-attachments/assets/ad6bff9c-d176-43c8-b232-ae5f28153399)


4. The magazine was not interested in any establishments in Dover, 
so checked how many documents contain the Dover Local Authority. 
Then, removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
![image](https://github.com/user-attachments/assets/a6ef2d4f-244e-4b9a-b346-dedf33e9b94a)
![image](https://github.com/user-attachments/assets/3fb2d0b4-10cb-4bc4-bb39-f30cf1ef7788)
![image](https://github.com/user-attachments/assets/0e19811c-5d0c-467f-ab03-96494b7abd56)
![image](https://github.com/user-attachments/assets/3f09e8dd-850c-42e9-87a9-58a0258a8363)
![image](https://github.com/user-attachments/assets/b5169112-e617-41c5-9f55-6c989731cd39)

5. Some of the number values were stored as strings, when they should be stored as numbers.    
- Used update_many to convert latitude and longitude to decimal numbers.
- Used update_many to convert RatingValue to integer numbers.
![image](https://github.com/user-attachments/assets/5bc73c5f-7b33-4c60-95e5-fb987550cebb)
![image](https://github.com/user-attachments/assets/bb828267-e9fc-4385-88b0-04338db45173)
![image](https://github.com/user-attachments/assets/6c438b0a-ef45-4e51-b8ea-c153875cdf9e)
![image](https://github.com/user-attachments/assets/f927c838-91aa-4bdc-8d2b-fa3c72e25318)
![image](https://github.com/user-attachments/assets/0f91c7e1-f25f-464a-9f41-f58654409ba0)
![image](https://github.com/user-attachments/assets/72ce5060-6d8e-4d39-a4c5-0299dbcce353)

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

![image](https://github.com/user-attachments/assets/b6005675-540f-4eb7-8f08-b709e2af920b)
![image](https://github.com/user-attachments/assets/9012d71f-3fbe-4b81-94ce-d4b82ded18be)

# Question 2: Which establishments in London have a RatingValue greater than or equal to 4?     

- A query was performed to find the establishments in London with a RatingValue greater than or equal to 4.    
- The query uses the "$regex" operator to locate the London establishments.       
- "count_documents()" was used to list the correct number of documents.    
- The first result was printed using pprint.    
- The results were converted to a Pandas DataFrame and displays the first 10 rows.

![image](https://github.com/user-attachments/assets/2c12f5b5-a571-49e1-9c44-2328bb001535)
![image](https://github.com/user-attachments/assets/25de0d39-c578-4636-b767-ad0186cd74b7)


# Question 3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?

- A query was performed to find the establishments within 0.01 degree of the "Penang Flavours" restaurant.    
- The query also limits the results to establishments with a RatingValue of 5.    
- The query uses the sort() method in PyMongo to sort in ascending order on the hygiene score.    
- The query uses the limit() method in PyMongo to limit the results to 5.    
- All five results were printed using pprint.    
- The results were converted to a Pandas DataFrame and displayed.

![image](https://github.com/user-attachments/assets/f5c83fa4-a3c5-49e3-9e38-3a08296dc4ee)
![image](https://github.com/user-attachments/assets/c6477e30-8204-4ca1-bea7-e524934a7633)


# Question 4: How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas. 

- An "aggregation pipeline" ws built to include a match query, group, and sort.     
- The match query matches documents with a hygiene score of 0.    
- The group step of the pipeline was grouped on LocalAuthorityName and counts the number of documents.    
- The sort step of the pipeline sorts the count of the documents in descending order.    
- The aggregation pipeline was correctly sent to the aggregate() method.    
- The results from the aggregation query was cast as a list and then saved to a variable.
- The first ten results were printed using pprint.    
- The results were converted to a Pandas DataFrame and displays the first 10 rows.
![image](https://github.com/user-attachments/assets/b92ec1de-da86-41b8-bb8f-2f41c4d61ad0)
![image](https://github.com/user-attachments/assets/eaaa2545-144b-4ed0-b60b-885387cebbe4)
![image](https://github.com/user-attachments/assets/c9b82784-57b5-4b55-839b-09a2d5106d45)
      
# Deployment Step further took place
