# Background
The UK Food Standards Agency evaluates various establishments across the United Kingdom, and gives them a food hygiene rating. 
You've been contracted by the editors of a food magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.

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
- Included the 'mongoimport' command text, have used to import 'establishments.json' in a markdown cell at the beginning of the Jupyter notebook file.   
- The mongoimport command text correctly dropped any existing establishments collection before importing establishments.json into MongoDB.  
- The database is named uk_food and the collection is named establishments.  
- Correctly imported PyMongo and Pretty Print.   
- An instance of the Mongo Client is created.   
- Listed the databases have in Mongo, which includes uk_food.    
- Listed the collection(s) in the uk_food database, which includes establishments in the output.    
- Used find_one() and pprint to display one document in the establishments collection.     
- The establishments collection is assigned to a variable.  
