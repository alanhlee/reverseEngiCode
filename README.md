# Reverse Engineering Code

### This md will explain what each file does/if it correlates to another file/how you would manipulate the code for any use desired.
--- 
- package.json
###### Showing you what dependencies this app will require to get started and which default js file is being run as the main.
- server.js
###### The main file on the top level that will be run when starting up your application. Including which port it will listen on what routes it requires and what express middleware is needed for this app. This also shows which routes we will be using for our application.
- README.md
###### What you're reading right now and breakdown of this application.
- /config
###### Contains a /middleware config.json + passport.js
1. config.json
###### Contains object for data structure we will be using within our application. Is required in /routes api-routes.js file
2. passport.js
###### Requires our package passport, provides functions used by passport function user login/verification with guards explicitly requiring their email and password that must match. This file is required in server.js 
3. /config/middleware isAuthenticated.js
###### Middleware REQUIRED in html-routes.js making sure a user is logged in to access the pages.
- /models
###### Datastructures used in database
1. index.js
###### Loads models from models directory onto sequelize object.
2. user.js
###### Creating user models for user and exporting into index.js within the models directory
- /public
###### Files that will be shown to the user containing javascript CSS HTML
1. login.html
###### The login in page that users will see.
2. members.html
###### The members page that users will see.
3. signup.html
###### The signup page that users will see.
- /public/js
###### Javascript files written for each page on the application.
1. login.js
###### Javascript file written for the login page has function to get email and password to pass to api routes.
2. members.js
###### Javascript file written for members page which has a function to check which users are logged in and update the page.
3. signup.js
###### Javascript file written for signup page which contains a function to post to signup routes
- /stylesheets
###### Contains CSS files to style our HTML pages
1. style.css
###### This styling file is required in login.html members.html signup.html
- /routes
###### Contains routes for /api's and html pages
1. api-routes.js
###### Returns/Handles API routes for JSON data
2. html-routes.js
###### Contains routes for HTML pages displayed to user for home page / - /login - /members
---

# Changes that may be applied
- styling (direct interface changes)
###### In the public folder you may change the style.css to recreate what every page looks like or create a stylesheet in the stylesheets folder and link the HTML page to that folder
- data structure (what our database structures look like)
###### In the models folder (user.js) the data model can be manipulated to what you see fit or even require a first and last name. This would be leading us to passport.js within the config folder with more (else if) statements
- requests (adding requests for put and delete)
###### In the routes folder within api-routes.js you may also choose to allow UPDATES to a user data with a PUT method within the function being updated or even deleted with a DELETE method.
