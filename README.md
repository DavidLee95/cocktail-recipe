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

### HTML page description (special thank you to [Boostrap](https://getbootstrap.com) for this section!)

- **Main menu (layout. html)**: The user can see the page's logo as well as click on 5 different menus according to his or her preference. In this page, a navbar from bootstrap was used on top so that independently of the page in which the user is lcoated, he or she may see all the options available in the navbar. In the center, the website's logo was added and to its right five options (anchor tags) were placed with different colors to direct the user to differet menus. Bootstrap's navbar was chosen because it is responsive to the screen size and its predefined functions were simple to use. On the last option, code was added so that when the user was logged in, the menu would display "Logout" and if the user was not logged in, the menu would display "Login". The rest of the space was left to use by the other HTML pages.
- **Homepage (index.html)**: In this page, the user will first see a welcome message and below it find a option to search a cocktail's recipe by typing its name. For this, an anchor tage was used to redirect the user to the search menu. On the main portion of the screen the user can find six drinks that are recommended by the website itself. Each drink has an image, name, review, and option the view the cocktail's recipe (for this a form was used with "post" as its method).The main portion of the page is all within a flexbox so that the content may be responsive to the screensize, adn the CSS was configured for such as purpose (display: flex, flex-wrap: wrap, justify-content: space-between, align-content: space-between, width: X*vw*, height: X*vh*, etc.). CSS was used so that each of the drinks may use the same space as the others and so that the name tag, review, and the recipe option might change position all depending on the position of the drink's image. After many tries, this ended up being the best solution in order to maintain order and good aesthetics independently of the screen size (all text, box, image sizes adapt to the screen size).
- **Login (login.html)**: The user writes his or her credentials to login in the website. In case that the user is not registered, he or she can choose to do so by clicking in the bottom "Register" option.
- **Register (register.html)**: This menu can only be accesed through the "Login" menu. In this menu, the user registers by writing a username and a password (2 times). In case that a username is already being used or first and second password do not match, the website will not allow the user to register.
- **Random Pick(random.html)**: When the user clicks this menu, a random cocktail's information appears as the result. Each time the user clikcs this menu the API will show randomly found cocktails as the result.
- **Recipe (recipe.html)**: This menu cannot be directly accesed by the user; it can only be accesed when a valid result is shown as a result of the "Search" and "Random Pick" pages' actions. In this menu, a cocktail's name, image, ingredients, and instructions appear. On the bottom of the page the user can choose to save the drink and see it directly in the "Saved" menu.
- **Saved (saved.html)**: In this menu, the user can see the cocktails that he or she has saved as well as remove any cocktails that he or she does not wish to keep saved anymore. 
- **Search (search.html)**: This menu allows the user to type the cocktail's name that the user wants to search for. In case that the user types a cocktail name that does not exist, the website flashes and error message.

### App.py file description:

This is the heart of the website's functionability. It defines the logic of each one of the html pages as well as other functions such as sessions or DB. Depending on the function, 



