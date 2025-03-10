


##### A FINAL PROJECT SUBMITTED TO THE UNIVERSITY OF CHICAGO IN PARTIAL FULFILLMENT OF THE REQUIREMENTS FOR THE COURSE OF MSCA 31008.3 DATA MINING PRINCIPLES

##### Peter Eusebio, Lola Johnston, Brea Beals, Jerry Sha, Roy Xie
##### Winter 2020

#### GitHub private repository: https://github.com/Pete-Best/genre-classification


## 1. Executive summary

## 2. Files in the repository

`README.md`: The readme file.

`DM_Project_Data_Cleaning.ipynb`: Jupyter Notebook file cleaning songdata.csv, extracting features, and preparing it for modeling  

`songdata.csv`: Original data with artist, song name, link, and lyrics for each song  

`genre collection.ipynb`: Jupyter Notebook pulling genres from spotify INSERT PETER'S DESCRIPTION 

`genres.pkl`:

`songs_wv_model`:

`veclyrics.pkl`: sparse matrix of the song lyrics


FINISH THIS LATER

## 3. Metadata for "response.pkl":
 - artist: Artist name
 - song: Name of song
 - genres: Genre of artist as pulled from Spotify
 - rock: Does the genre list contain the substring: “rock”?  (0 if the substring is not present in genre, 1 if it present)
 - singer-songwriter: Does the genre list contain the substring: “singer-songwriter”? (0 if the substring is not present in genre, 1 if it present)
 - pop: Does the genre list contain the substring: “pop”? (0 if the substring is not present in genre, 1 if it present)
 - metal: Does the genre list contain the substring: “metal”? (0 if the substring is not present in genre, 1 if it present)
 - folk: Does the genre list contain the substring: “folk”? (0 if the substring is not present in genre, 1 if it present)
 - country: Does the genre list contain the substring: “country”? (0 if the substring is not present in genre, 1 if it present)
 - hip hop/rap: Does the genre list contain the substring: “hip hop” or "rap"? (0 if the substring is not present in genre, 1 if it present)
 - tokenstring: Original song lyrics that have been cleaned, lemmatized, and tokenized. Cleaning process is defined below in Section 4. Methodology.

## 4. Methodology

**Section 4.1: Pulling Genre Date From Spotify**

**Section 4.2: Cleaning and Pre-Processing** 

1. Deleted all round brackets, square brackets, and text within square brackets, and line breaks
2. Removed non-english songs. Found the probability of a song being English and removed all songs with a probability lower than 0.5
3. Lemmatized and preprocessed the text data using gensim simple_preprocess and saved under "text_preprocessed"
4. Tokenized the data and saved under "tokens"
5. Removed stop words from "tokens" using the package stopwords from ntlk
6. Ran a word2vec model to explore relationships between words
7. Applied Count Vectorizer() to transform "tokens" into vectors

**Section 4.2: Creating Models** 

1. Import data- 

   veclyrics = np.load('veclyrics.pkl',allow_pickle = True)
   
   
   df = pd.read_pickle("response.pkl")
   
   
   X_train, X_test, y_train, y_test = train_test_split(veclyrics, df['pop'], test_size = 0.2, random_state = 1)
   
    - split for each genre ('pop' in example)

**Section 4.3: Comparing and Selecting Model** 

**Section 4.3: Validating on New Dataset** 



