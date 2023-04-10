# Food Recipes
#### Video Demo:  <https://www.youtube.com/watch?v=aLRq9LO-Acc>
#### Description:

This is a food recipe website that I made using python's flask and html/css/javascript whose purpse is to be able to find recipes that other people created on the website or even create your own. The website is using werkzeug.security as per pset9 in order to encrypt the user's password and then save the user's credentials (username, email and hash).

Users can start browsing recipes as soon as they enter the website without being registered and/or logged in. There is a search field that takes up to 2 words to search a dish's name or ingredients, as well as a Sort By option for latest uploads (3 to be exact) or by Name asc and desc. Upon pressing Browse in the navbar they are brought to a list of recipes with a photo and the name of the dish with the ability to click on the recipe and get the ingredients and instructions for the dish.

By registering and logging in, users gain the ability to upload their own recipes by clicking "Share your dish" in the navbar which are then redirected to the coresponding url that contains a form with the dish's name, the ingredients and the instructions. Optionally you can upload a photo of the dish, otherwise a default photo will be put instead. Recipes that users created can be found in the "Control Panel" labeled as "My recipes" where they have the ability to edit them, changing the name, ingredients, instructions or the photo. Photos are being saved in an image folder with the recipe_id infront of the photo's name under static, instead of a blob inside the db, and the path to the photo is instead saved in the db.

Speaking of the Control Panel users get a couple more options if they choose to register/login, the ability to add recipes to a favorites list for easy access next time they need them. As users browse the recipes, if they are logged in they can see a red heart icon which upon clicking it, adds the recipe to their favorites list which can be accessed by clicking "Favorites" under the Control Panel. In Favorites they can see every recipe that they have favorited with the ability to click the grey heart this time in order to unfavorite. Recipes that the users have in their favorites list no longer have a red heart icon, meaning they are already in the Favorites.

Lastly there is a "Settings" option in the Control Panel that upon clicking it give you three options, to change your password, your username or your email. The username and email are unique so there are no two of the same usernames or emails in the database. If you try to change any of them and the username is taken or the email is already registered by someone else you get an error message that explains that, same way when the user registers they have to have a unique username and email.

The website is use a recipes.db with tables user (for user credentials), recipes (to save the dish name, ingredients, instruction, photo, *creator_id) and favorites (which servers as a relation between the user and the dish using the recipe_id and user_id)

What I really regret not implementing is a page system for the recipes, so instead of having a very long list of them I wanted to have 5 per page but proved to be hard for me to implement. I also don't like the fact that the website doesn't scale well with smaller monitors but I think that's something I should've tried to do early on, by the time i realised it was already a month later.

*The reason I have a creator_id in the recipes table is because initially i had the username of the person who created the recipe, appear next to the red heart icon (to add recipe to favorites) with the intention to make it clickable so you could see every recipe this user uploaded but I scrapped that due to the project taking too long to finish already