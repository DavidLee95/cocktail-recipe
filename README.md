# cocktail-recipe

A website to search and save cocktail recipes!

## About cocktail-recipe:

This website allows users to search their favorite' cocktails recipe in a variety of ways. The website itself has several different pages (homepage, search, and random) by which the users can obtain the cocktail's recipes depending on whether they directly type in the name of a cocktail, click on the recommended cocktail's recipes or get randomly suggested cocktail recipes. Independently of which path the user chooses to obtain a cocktail's recipe, the final result will be displayed in another page that will contain the name, image, ingredients, and instructions to prepare the cocktail. The website itself requires the user to be logged in in order to access all the features that it offers (a registration page is also avilable), and by logging in the user can save cocktail recipes of his or her choice to view them in the future. 

Most importantly, the website makes use of the Cocktail DB API which can be found at [Cocktail DB](https://www.thecocktaildb.com/api.php). A round of applause and a special appreciation to the cocktail db's administrators for such an awesome API!

## Project files:

- flask_session: Information regarding flask's session.
- static: Where the CSS and image files are located.
- templates: Where the HTML files are located.
- app.py: The project's main python code.
- subcode.py: Where the project's sub python codes are located to be used in the app.py file.
- users.db: Where the user's login credentials and saved cocktail information are located.

### HTML page description (special thank you to [Boostrap](https://getbootstrap.com) during this section!)

- **Main menu (layout. html)**: The user can see the page's logo as well as click on 5 different menus according to his or her preference. In this page, a navbar from bootstrap was used on top so that independently of the page in which the user is lcoated, he or she may have access to the navbar all the time. In the center, the website's logo was added and to its right five options (anchor tags) were placed with different colors to direct the user to differet menus. Bootstrap's navbar was chosen because it is responsive to the screen size and its predefined functions were simple to use. On the last option, code was added so that when the user was logged in, the menu would display "Logout" and if the user was not logged in, the menu would display "Login". The rest of the space was left to use by the other HTML pages.

- **Homepage (index.html)**: In this page, the user will first see a welcome message and below it find a option to search a cocktail's recipe by redirecting him or her to the search menu by using an anchor tag. On the main portion of the screen the user can find six drinks that are recommended by the website itself. Each drink has an image, name, review, and option to view the cocktail's recipe (for this a form was used with "post" as its method and redirects the user to the recipe.html page).The main portion of the page is all within a flexbox so that the content may be responsive to the screensize, adn the CSS was configured for such as purpose (display: flex, flex-wrap: wrap, justify-content: space-between, align-content: space-between, width: X*vw*, height: X*vh*, etc.). CSS was used so that each of the drinks may use the same space as the others and so that the name tag, review, and the recipe option might position themselves relative to the drink image. After many different tries, this ended up being the best solution in order to maintain order and good aesthetics independently of the screen size (all text, box, image sizes adapt to the screen size).

- **Login (login.html)**: The user writes his or her credentials to login in the website. In case that the user types a username that does not exist, a flash message appears telling the user so. If the username does exist but the password is incorrect, again a flash message appears telling the user so. Instead of redirecting to the user to an error page, flash messages were used because it elimitaes the need to craete another "error" html page as well as it is visually more attractive. The *login* button is a form with "post" as its method that runs a python code in the app.py file. In case that the user is not registered yet, he or she can choose to do so by clicking in the bottom "Register" option, which is an anchor tag that redirects the user to the register page.

- **Register (register.html)**: This menu can only be accesed through the "Login" menu (it is not available in the navbar). In this menu, the user registers by writing a username, a password, and the password's confirmation. In case that a username is already being used, a flash message appears telling the user that the username is unavailable. In case that password and the confirmation do not match, another flash message appears telling the user that both informations do not match. The *register* button is a form with "post" as its method that runs a python code in the app.py file.

- **Recipe(recipe.html)**: When the user searches for random drinks or a specific drink, a cocktail's information (name, image, ingredients, and instructions) appears as the result by using the API provided by Cocktail DB. The information that appears is all within a flexbox that on the left has the image and on the right the ingredients and instructions within a box. CSS was used to setup this flexbox so that it would adapt the the screen size, and so that the image and information would not overlap. Once in this menu, the user can see the result provided by the website, and if he or she would like to save this drink it can be done by simply clicking on the "Save Drink" button available on the bottom of the page (this button is a form with "post" as its method). The user can later view this item in the "Saved" menu. 

- **Saved (saved.html)**: In this menu, the user can see the cocktails that he or she has saved as well as remove any cocktails that he or she does not wish to keep saved anymore. This page uses jinja in order to extract a list that it gets by extracting information from the users_db. A table obtained from Bootstrap is used to display the information and has five rows in it (number, name, image, see recipe, and remove cocktail). A Bootstrap table was chosen because it makes the whole page look organized and clean. The number of columns depends on the number of cocktails saved by the user. The DB simply gives the html page the cocktail's name, and with it the page searches and displays the necessary information by principally using the Cocktail DB API. The user can click on the "Get the xxxxxx Recipe!" form (with "post" as its method) to go see the recipe to the "recipe.html" page and also clikc on the "Remove xxxxxx" form (with "post" as its method) to remove the cocktail from the DB.

- **Search (search.html)**: This menu allows the user to type the cocktail's name that the user wants to search for. In case that the user types a cocktail name that does not exist, the website flashes an error message. In case that the user does type a cocktail that does exist, it redirects the user to the "recipe.html" page to display the cocktail recipe that the user is searching for. The page uses a form with a "search" input and button with "post" as its method in order to request the cocktail's search.

### App.py file description:

This is the heart of the website's functionability. It defines the logic of each one of the html pages as well as other functions such as sessions or DB. This file imports the following libraries in order to function well:

'''python
from cs50 import SQL
from flask import Flask, redirect, render_template, request, session, flash
from flask_session import Session
from werkzeug.security import check_password_hash, generate_password_hash
from subcode import user_search, random_search, login_required
'''

The functions within the app.py file are the following:

- **Main menu (layout. html)**: 

- **Homepage (index.html)**: 

- **Login (login.html)**: 

- **Register (register.html)**: 

- **Recipe(recipe.html)**: 

- **Saved (saved.html)**: 

- **Search (search.html)**: 



