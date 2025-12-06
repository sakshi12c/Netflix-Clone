A feature-rich Netflix clone web application that displays trending movies, categorized movie collections, and integrated YouTube trailers using The Movie Database (TMDB) API.
OVERVIEW
This is a fully functional Netflix clone built with vanilla HTML, CSS, and JavaScript. The application fetches real-time movie data from TMDB API, displays trending content in a dynamic banner section, organizes movies by genres, and plays YouTube trailers on hover.
FEATURES
Dynamic Banner Section: Displays a randomly selected trending movie with backdrop image, title, release date, and overview
Trending Movies: Dedicated section showcasing current trending movies
Genre-Based Categories: Movies organized by genres (Action, Comedy, Drama, Horror, etc.)
YouTube Trailer Integration: Automatic trailer playback when hovering over movie posters
Responsive Header: Navigation bar with search and notification icons that changes background on scroll
Smooth Scrolling: Optimized scrolling experience with fade effects
Responsive Design: Mobile-friendly interface that adapts to different screen sizes
Auto-playing Trailers: Embedded YouTube videos with autoplay on hover
FILE STRUCTURE
project/
index.html      Main HTML structure and layout
index.css       Complete styling and responsive design
index.js        JavaScript functionality and API integration
favicon.ico     Browser tab icon (optional)
TECHNOLOGIES USED
HTML5
CSS3 (Flexbox, Grid, Animations)
JavaScript (ES6+)
TMDB API (The Movie Database)
YouTube Data API v3
APIS USED
The Movie Database (TMDB) API
Used for fetching movie data, genres, and trending content
API Key included in code: e950e51d5d49e85f7c2f17f01eb23ba3
YouTube Data API v3
Used for searching and embedding movie trailers
API Key included in code: AIzaSyA_eZ5WJhmYhRQOM8-jAyVIzzdfWUlp_P0
INSTALLATION AND SETUP

Download all project files to a single directory
Ensure you have an active internet connection (required for API calls)
Open index.html in any modern web browser
The application will automatically load trending movies and categories

No additional installations, dependencies, or build tools required.
USAGE
Browsing Movies
Upon loading, the application displays a featured trending movie in the banner section with play and more info buttons
Scroll down to explore movies organized by different genres
Each genre section shows 6 movies from that category
Viewing Trailers
Hover over any movie poster to automatically load and play its YouTube trailer
The trailer will appear as an overlay on the movie poster
Move your mouse away to stop the trailer
Movie trailers are fetched in real-time from YouTube based on movie titles
Header Navigation
The header remains fixed at the top while scrolling
Background becomes opaque (black) after scrolling down 5 pixels
Navigation menu includes: Home, TV Shows, Movies, News & Popular, My List, Browse by Languages
Search and notification icons available in the right corner
HOW IT WORKS
Application Initialization
On page load, the init() function executes two main processes:
Fetches trending movies and builds the banner section
Fetches all movie genres and builds category sections
Banner Section
Randomly selects one movie from trending results
Displays movie backdrop as background image
Shows movie title, release date, and overview (truncated to 200 characters)
Includes Play and More Info action buttons
Movie Categories
Fetches complete list of movie genres from TMDB
For each genre, fetches up to 6 movies
Dynamically builds movie sections with poster images
Each movie is displayed with its backdrop image
Trailer Functionality
When user hovers over a movie poster, searchMovieTrailer function is triggered
Searches YouTube for the movie title trailer
Embeds the first search result as an autoplay iframe
Trailer appears in a div overlay on the movie poster
Scroll Effects
Listens for scroll events on window
Adds black-bg class to header when scroll position exceeds 5 pixels
Removes class when scrolled back to top
CUSTOMIZATION
Changing API Keys
To use your own API keys, edit the following in index.js:
const apikey = "YOUR_TMDB_API_KEY";
YouTube API key in apiPaths object:
key=YOUR_YOUTUBE_API_KEY
Adjusting Movie Count
To change the number of movies displayed per category, modify this line in fetchAndbuildMovieSection function:
buildMoviesSection(movies.slice(0,6), categoryName);
Change 6 to your desired number.
Styling Modifications
Edit index.css to customize:
Background colors: body background-color and header.black-bg
Banner height: .banner-section min-height
Movie poster size: .movie-item width
Font families and sizes throughout
Banner Content Display
To adjust overview text length, modify this line in buildBannerSection function:
movie.overview.slice(0,200)
Change 200 to your preferred character count.
KEY FUNCTIONS
init()
Initializes the application by fetching trending movies and all category sections
fetchTrendingMovies()
Fetches trending movies and randomly selects one for the banner
buildBannerSection(movie)
Creates and displays the banner section with movie details
fetchAndBuildAllSections()
Fetches all movie genres and builds category sections
fetchAndbuildMovieSection(fetchUrl, categoryName)
Fetches movies for a specific category and builds the section
buildMoviesSection(list, categoryName)
Creates HTML structure for movie category sections
searchMovieTrailer(movieName, iframeId)
Searches YouTube for movie trailer and embeds it
RESPONSIVE DESIGN
Desktop: Full navigation menu with all features visible
Mobile (max-width: 767px):
Navigation menu hidden (hamburger menu not implemented)
Banner title and overview expand to 100% width
All other features remain functional
KNOWN LIMITATIONS
Navigation menu items are not functional (display only)
Search and notification icons have no functionality
Play and More Info buttons in banner section have no action handlers
Mobile navigation menu not implemented (items hidden on mobile)
Trailer search uses movie title which may not always return accurate results
API keys are exposed in client-side code (not production-ready)
No error handling UI for failed API requests
Trailers may not load if YouTube API quota is exceeded
Limited to 6 movies per category
No movie detail pages or player functionality
PERFORMANCE CONSIDERATIONS
API calls are made sequentially for each genre which may cause slower initial load
YouTube iframes are created on every hover which could impact performance
No caching mechanism implemented for API responses
Images are loaded from TMDB CDN (external dependency)
Multiple API requests made on page load
FUTURE ENHANCEMENTS
Implement functional navigation menu items
Add search functionality with results page
Create movie detail modal or page
Add user authentication and profiles
Implement My List feature with local storage or backend
Add video player functionality for Play button
Create responsive mobile navigation menu
Implement lazy loading for images and videos
Add error handling and loading states
Cache API responses to reduce requests
Implement pagination for movie categories
Add filter and sort options
Include TV shows functionality
Add user ratings and reviews
Implement watchlist and viewing history
BROWSER COMPATIBILITY
This application works on all modern browsers:
Chrome (recommended)
Firefox
Safari
Edge
Opera
Note: Internet Explorer is not supported due to ES6+ JavaScript usage.
CREDITS
Movie data provided by The Movie Database (TMDB)
Trailer videos from YouTube
Netflix logo and design inspiration from Netflix
DISCLAIMER
This is a clone project created for educational purposes only. It is not affiliated with, endorsed by, or connected to Netflix in any way. All movie data and images are property of their respective owners.
API USAGE NOTES
TMDB API is free but has rate limits
YouTube Data API has daily quota limits (default: 10,000 units per day)
For production use, implement proper API key management and backend proxy
Never expose API keys in production client-side code
TROUBLESHOOTING
Movies not loading: Check internet connection and verify API keys are valid
Trailers not playing: YouTube API quota may be exceeded or video embedding disabled
Banner not displaying: Check console for CORS or API errors
Scroll effect not working: Ensure JavaScript is enabled in browser
Images not loading: TMDB CDN may be temporarily unavailable
SUPPORT
For bugs or issues, check the browser console for error messages
Verify all files are in the same directory
Ensure active internet connection for API access
Check that API keys have not expired or exceeded quota limits
