# Title
Module 6 Data Sourcing Challenge

## Source Data
Data is sourced from two open APIs: 
1. The New York Times API
2. The TMDB Movie API

Below are the referenced URLs for using the APIs:
1. The New York Times API: https://developer.nytimes.com/docs/articlesearch-product/1/overview
2. The TMDB Movie API: https://developer.themoviedb.org/docs/search-and-query-for-details

## APIs Usage and Keys
This assignment shows how to open and use APIs, using multiple URLs, passing api keys/tokens, parameter passing to retrieve data, parsing JSON format.

## Data Retrieval and Preparation
The movie reviews data is retrieved from the New York Times API and the reviews are stored from 20 different pages and stored in a list. json.dumps is used for formatting the data. The the review data in the list is converted to a pandas dataframe using the `pd.json_normalize` function. I extracted the movie title from the data frame after doing some data analysis on the title pattern and stored the movie titles in a list. I have used the `re` module for extracting the title which is a very powerful tool for pattern searching & matching. Next I used the NYT movie title list to search for the movie details in the TMDB API, retrieve the data, store it in a seperate TMDB movie list & format it data using json.dumps. The the data is then finally stored in a pandas dataframe. I finally merge the two dataframes (Inner join on the movie title ) into a final dataframe, did the required data cleaning and stored the cleaned dataframe in a csv file.

## Protecting Personal API Keys & Tokens
The API keys and tokens are stored in a seperate file API_Key.env which is being excluded from the git repository using the .gitignore file. The API keys are read from the file using the `os` module and stored in a variable. The variable is then used in the API call.