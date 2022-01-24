# movies_ETL
## Data Analytics Mod 8
### Project Overview
Background
Amazing Prime loves the dataset and wants to keep it updated on a daily basis. Britta needs your help to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. You’ll need to refactor the code from this module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.

### Scope
Deliverable 1: Write an ETL Function to Read Three Data Files
Deliverable 2: Extract and Transform the Wikipedia Data
Deliverable 3: Extract and Transform the Kaggle data
Deliverable 4: Create the Movie Database

#### Deliverable 1: Write an ETL Function to Read Three Data Files (25 points)

##### Jupyter Notebook Code
![image](https://user-images.githubusercontent.com/94234511/150722423-16abdb46-e478-46bd-b09f-e2cd7e341c33.png)

##### The wiki_movies_df DataFrame
![image](https://user-images.githubusercontent.com/94234511/150722460-7501df2d-3759-4d7f-859a-06e2af11a622.png)

##### The kaggle_metadata DataFrame
![image](https://user-images.githubusercontent.com/94234511/150722487-80cf2790-979c-4f2a-b8b2-801ec5c4d24d.png)

##### The ratings DataFrame
![image](https://user-images.githubusercontent.com/94234511/150722511-960cb64a-b6d8-4b48-a64f-f53fd5962128.png)

https://github.com/cherylberger/movies_ETL/blob/main/ETL_function_test.ipynb


#### Deliverable 2: Extract and Transform the Wikipedia Data (30 points)

##### Perform List Comprehension to filter out TV shows from the wiki_movies_raw file.
![image](https://user-images.githubusercontent.com/94234511/150722605-f24e62e1-e782-4b83-bf8d-2b665f4dc594.png)

##### Write a try-except block that will catch errors while extracting the IMDb IDs with a regular expression string and dropping any imdb_id duplicates. If there is an error, capture and print the exception.
![image](https://user-images.githubusercontent.com/94234511/150722637-cd236567-af00-40fc-aabd-5d1522c3d3e6.png)

##### Clean and convert the box office data created to string values using the lambda and join functions.
![image](https://user-images.githubusercontent.com/94234511/150722679-4dd94b03-8835-442b-8d51-9c81af4bcac6.png)

##### In step 10, write a regular expression to match the six elements of form_one and form 2 of the box office data.
![image](https://user-images.githubusercontent.com/94234511/150722758-3bd4dace-e06f-483a-a354-8dd5d382123c.png)

##### In Step 12, add the parse_dollars() function.
![image](https://user-images.githubusercontent.com/94234511/150722789-f8d778a8-40bc-4273-ae3a-eb0124ab2c31.png)

##### clean the box office, budget, release date and running time columns
![image](https://user-images.githubusercontent.com/94234511/150722829-84aa3323-01c8-4e46-9435-cf3720d9d53e.png)

##### Create a path to the Wikipedia data, the Kaggle metadata, and the MovieLens rating data files and set the three variables equal to the function created in Deliverable 1, also set the wiki_movies_df equal to the wiki_file variable.
![image](https://user-images.githubusercontent.com/94234511/150722916-38053bf3-7c40-4e35-882f-fc8400e57401.png)

##### wiki_movies_df
![image](https://user-images.githubusercontent.com/94234511/150722956-270d79af-b58b-4a5f-bbe3-93875d058c74.png)

##### wiki_movies_df DataFrame to a list,
![image](https://user-images.githubusercontent.com/94234511/150722974-44aded79-f3d2-44f4-89f7-e107177a5c2e.png)

ETL_clean_wiki_movies.ipynb

#### Deliverable 3: Extract and Transform the Kaggle Data (30 points)

##### In Step 2, below the code that cleans the running time column in the wiki_movies_df DataFrame from Deliverable 2, add the code that cleans the Kaggle metadata.
![image](https://user-images.githubusercontent.com/94234511/150723536-41f3a589-fb44-4efc-9c31-deffe352e03a.png)

##### merge the wiki_movies_df DataFrame and the kaggle_metadata DataFrames, then name the new DataFrame, movies_df.
![image](https://user-images.githubusercontent.com/94234511/150723587-04dd7fe3-9ae4-441d-b97e-44ea0a01ced2.png)

##### Clean the merged DataFrame
![image](https://user-images.githubusercontent.com/94234511/150723623-e5787957-a557-4896-95eb-0c595959e14a.png)

##### rename the columns in the movies_df DataFrame.
![image](https://user-images.githubusercontent.com/94234511/150723653-2da49e8f-4903-4a7a-a448-a5e38f798096.png)

##### transform and merge the ratings DataFrame with the movies_df DataFrame, name the new DataFrame movies_with_ratings_df, then clean the movies_with_ratings_df DataFrame.
![image](https://user-images.githubusercontent.com/94234511/150723682-2da67082-a550-4ea1-9413-f5a602fb9d66.png)

##### check that your wiki_movies_df DataFrame is the same as in Deliverable 2.
![image](https://user-images.githubusercontent.com/94234511/150723741-b110df38-4598-42cf-b25c-a910c3d3109e.png)

##### movies_with_ratings_df
![image](https://user-images.githubusercontent.com/94234511/150723768-32887cd1-8de4-4b20-b404-003bcf915e1b.png)

##### movies_df
![image](https://user-images.githubusercontent.com/94234511/150723798-1ff215f8-6354-4653-a02e-955709321732.png)

https://github.com/cherylberger/movies_ETL/blob/main/ELT_clean_kaggle_data.ipynb

#### Deliverable 4: Create the Movie Database (15 points)

from config import db_password

Transform and merge the ratings DataFrame, add the code to create the connection to the PostgreSQL database, then add the movies_df DataFrame to a SQL database.R
![image](https://user-images.githubusercontent.com/94234511/150723227-42396ea0-e884-4b9d-87fa-5736ba9be232.png)

Add the code that prints out the elapsed time to import each row.
![image](https://user-images.githubusercontent.com/94234511/150723315-38999cbc-57f8-43c8-8f1a-bfa6dd6d25bb.png)

Refactor Step 11 of Deliverable 3 so that you pass in the variables for the files created in Step 10 of Deliverable 3 in the function created in Deliverable 1.
![image](https://user-images.githubusercontent.com/94234511/150723059-1f9120b1-8942-4166-9dd3-528c38927dfe.png)

run a query on the PostgreSQL database that retreives the number of rows for the movies and ratings tables.

movies_query.png 

ratings_query.png

https://github.com/cherylberger/movies_ETL/blob/main/ELT_create_database.ipynb
