# MovieClub
## Movie Recommendation System based on Content Based Filtering extracting 7 features out of Dataset
### Load the data set and extract  features
### selected_features = ['genres','keywords','tagline','cast','director','vote_average','popularity']

## Used TfidfVectorizer() to create a vector space of integers using concatenated features variable for each movie
### combined_features = movies_data['genres']+' '+movies_data['keywords']+' '+movies_data['tagline']+' '+movies_data['cast']+' '+movies_data['director']+' '+str(movies_data['vote_average'])+' '+ str(movies_data['popularity'])
### vectorizer = TfidfVectorizer()
### feature_vectors = vectorizer.fit_transform(combined_features)

## found array of closed matches for user inputs using difflib library 

## Used the Algorithm of Cosine Similarity (Angular distance between two values on 2D plot) to create similarity matrix  according to values of array of close matches to User Input
### similarity = cosine_similarity(feature_vectors)

## Sort the movies according to  similarity value present at 1st index i.e x[1]  in Descending order (Higher similarity first)
### sorted_similar_movies = sorted(similarity_score, key = lambda x:x[1], reverse = True)

## Create three lists and append the information of top 15 movies recommended their name, genre, homepage website values in it, and pass the lists to HTML frontend via Flask backend
### return flask.render_template('positive.html',movie_names=names,movie_date=genre,movie_dir=dir, search_name=m_name)


### Open for Collab!
