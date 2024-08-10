Popcorn Bits Cinema
Description/Overview
Popcorn Bits Cinema is a movie app made with HTML, CSS, Javascript, jQuery and Bootstrap. It pulls movies from The Movie Database using API calls. Users have the option to view the top playing movies, sort them by genre or search for other movies using the search function.

Live URL

GitHub Repo

Table of contents
Description/Overview // GitHub Link // Technologies Used // Challenges and Solutions // Code Snippets and Screenshots

Technologies
The following languages, frameworks and APIs were used:

HTML

CSS

Javascript

jQuery

Bootstrap

The Movie Database API

Challenges and Solutions
Challenge: One of the challenges was making sure that the modal would display details on whichever movie was clicked on. Originally, the modal would only display the details for most recent movie (first movie from left to right) no matter which poster was clicked on. This was true without regard to whether the movies were sorted by genre or displaying the latest movies.

Solution: While building the HTML string, I had to include i in the modal portion of the new HTML string to target each clicked poster.

Challenge: Despite having a correctly built HTML, the searched movie(s) did not show when the user clicked "Submit".

Solution: Just running the searchMovies function when the form is submitted did not work because the movieGrid id already has an HTML attached to it. I couldn't overwrite it using .html(). As a result, I decided to run searchMovies with an empty query string before a search term is captured. When a user types in a search term, the function is ran again with the search term as an endpoint. This time, the new HTML string will overwrite the one created from the empty string search.

var searchTerm = '';
searchMovies();
//reference entire search form
$('.searchForm').submit(function(event){
	$('#movie-grid').html('');
	event.preventDefault();
	//search term is only concerned with what the user inputted 
	//Get input with .val();
	searchTerm = $('.form-control').val();
	searchMovies();
})
