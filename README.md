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

{    
    "BusinessName":"Penang Flavours",    
    "BusinessType":"Restaurant/Cafe/Canteen",    
    "BusinessTypeID":"",    
    "AddressLine1":"Penang Flavours",    
    "AddressLine2":"146A Plumstead Rd",    
    "AddressLine3":"London",    
    "AddressLine4":"",    
    "PostCode":"SE18 7DY",    
    "Phone":"",    
    "LocalAuthorityCode":"511",    
    "LocalAuthorityName":"Greenwich",    
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",    
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",    
    "scores":{    
        "Hygiene":"",    
        "Structural":"",    
        "ConfidenceInManagement":""    
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },    
    "RightToReply":"",    
    "Distance":4623.9723280747176,    
    "NewRatingPending":True    
}    

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
