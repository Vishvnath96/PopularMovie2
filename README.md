# PopularMovies - Android App - Stage 2

Popular-Movie2 app as part of  Android nanodegree assignment.

This app uses service - http://api.themoviedb.org/3/movie/popular to fetch most popular / highest rated movies and display to the user.
user can change sort order from settings menu

# API KEY
Please put your api key in Constant.java file as below:

`API_KEY = "<your key>"`



# Project specifications:

### User Interaction - Layout:
  
Movies are displayed in the main layout via a grid of their corresponding movie poster thumbnails.

UI contains a screen for displaying the details for a selected movie.

Movie Details layout contains title, release date, movie poster, vote average, and plot synopsis.

Movie Details layout contains a section for displaying trailer videos and user reviews.



### User Interface:
   


When a user changes the sort criteria (most popular, highest rated) the main view gets updated correctly.

When a movie poster thumbnail is selected, the movie details screen is launched.

When a trailer is selected, app uses an Intent to launch the trailer.

In the movies detail screen, a user can tap a button (for example, a star) to mark it as a Favorite. Tap the button on a favorite movie will unfavorite it.



### Network Layer Implementation:
   


In a background thread, app queries the /movie/popular or /movie/top_rated API for the sort criteria specified in the settings menu.

App requests for related videos for a selected movie via the /movie/{id}/videos endpoint in a background thread and displays those details when the user selects a movie.

App requests for user reviews for a selected movie via the /movie/{id}/reviews endpoint in a background thread and displays those details when the user selects a movie.



### Data Persistence Layer:
    

The titles and IDs of the user’s favorite movies are stored using Room and are updated whenever the user favorites or unfavorites a movie. No other persistence libraries are used.


When the "favorites" setting option is selected, the main view displays the entire favorites collection based on movie ids stored in the database.


### Android Architecture Components

Database is implemented using Room. No other persistence libraries are used.

Database is not re-queried unnecessarily. LiveData is used to observe changes in the database and update the UI accordingly.

Database is not re-queried unnecessarily after rotation. Cached LiveData from ViewModel is used instead.


Implement sharing functionality to allow the user to share the first trailer’s YouTube URL from the movie details screen.

