# Netflix GPT

- Create React App
- Configured TailwindCSS
- Header
- Routing of App
- Login Form
- Sign up Form
- Form Validation
- useRef Hook
- Firebase Setup
- Deploying our app to production
- Create SignUp User Account
- Implement Sign In user Api
- Created Redux Store with userSlice
- Implemented Sign out
- Update Profile
- BugFix: Sign up user displayName and profile picture update
- BugFix: if the user is not logged in Redirect /browse to Login Page and vice-versa
- Unsubscibed to the onAuthStateChanged callback
- Add hardcoded values to the constants file
- Regiter TMDB API & create an app & get access token
- Get Data from TMDB now playing movies list API
- Custom Hook for Now Playing Movies
- Create movieSlice
- Update Store with movies Data
- Planning for MainContauiner & secondary container
- Fetch Data for Trailer Video
- Update Store with Trailer Video Data
- Embedded the Yotube video and make it autoplay and mute
- Tailwind Classes to make Main Container look awesome
- Build Secondary Component
- Build Movie List
- build Movie Card
- TMDB Image CDN URL
- Made the Browsre page amazing with Tailwind CSS
- usePopularMovies Custom hook
- GPT Search Page
- GPT Search Bar
- (BONUS) Multi-language Feature in our App)
- Get Open AI Api Key
- Gpt Search API Call
- fetched gptMoviesSuggestions from TMDB
- created gptSlice added data
- Resused Movie List component to make movie suggestion container
- Memoization
- Added .env file
- Adding .env file to gitignore
- Made our Site Responsive

# Features

- Login/Sign Up
  - Sign In /Sign up Form
  - redirect to Browse Page
- Browse (after authentication)
  - Header
  - Main Movie
    - Tailer in Background
    - Title & Description
    - MovieSuggestions
      - MovieLists \* N
- NetflixGPT
  - Search Bar
  - Movie Suggestions

# Project Setup

- Before starting the project please add .env file and add TMDB and OPENAI KEY into it.

Steps to deploy react app on firebase->
Install firebase CLI -> npm install -g firbase-tools
firebase login
firebase init - select an option called Hoisting: Configure files for Firebase hosting and (optionally) set up Github Action deploy
use an existing project - select the project name
public directory - build
Configure as a single-page app (rewrite all urls to /index.html) - type no
set up automatic builds and deploys with Github - type no
run "npm run build" command
run "firebase deploy" command

<!-- ---------------------------------------- -->

<!-- Firebase setup -->

1. npm i firebase

2. Add Firebase SDK -> create firebase.js file (refer the current code) and paset the sdk from firebase document.

3. go to project overview and enable authentication -> project overview -> authentication -> get started -> sign method -> enable email/password

4) go to firebase doc and then go to authentication -> web -> password authentication -> create a password-based account (option2) (web modular api) -> copy "const auth = getAuth" and also copy "import { getAuth } from "firebase/auth" into firebase.js file which you created as we need this in every api call signin/signup etc, so keep it like this in a separate file. whenver I will need this auth, i will just import it from this firebase.js file. Now copy the code for signup and signin accordingly from the doc(refer the code in "Login.js" file).

5) We are saving the user data in redux store whenever a user sign in or sign up. For this we have to dispatch an action in signin api and signup api. Firebase gives us an api called "onAuthStateChanged" unser manage user section, this api gets called whenever a user sign in/sign up/sign out etc or we can say whenever an authentication state gets changed, means whenever sign in /sign up/sign out etc happens and you want to do something on this auth change then we can use this api. this is like an event listener.

<!-- -------------------------------- -->

<!-- TMDB -->

go to TMDB doc -> click on user icon and click on edit profile -> API -> copy API Key and API access token -> go to documentation -> api reference -> choose movie lists api -> copy fetch request options into "constants" file(refer current code) as we have to pass always whenever we will make an api call for TMDB ->

<!-- ---------------------------- -->

<!-- For gpt api -->

go to platform.openai.com -> personal -> view api keys -> create new secret key by any name and after creating it add it into constant file(refer current source code) -> go to open i package (npm) -> run "npm i --save openai" command -> code is written in openai.js file under utils folder
