# my-fitness-buddy
Homework - a PHP-based food-tracking app.




Week 20 - Homework Instructions
Overview

For this assignment, you'll create an application called My Fitness Buddy (MFB), a lightweight version of My Fitness Pal's calorie tracker.

MFB's primary functionality is as follows:

Allow users to login to their accounts;
Add meals they eat throughout the day, along with the foods that comprise the meal;
Track mactronutrient data for each food (protein, carbohydrates, fat);
Display meals the user has eaten today on the user's dashboard.
You can view an example implementation here.

Before You Begin

We'll be using MySQL for this assignment, so make sure your server is configured correctly. Be sure you remember your database username and password, as well.
Instructions

Setup

Create a new Laravel project and cd into it.
Serve your app to make sure you're ready to get started.
Initialize a new Git repository and make your initial commit.
Tasks

Create a new MySQL database for your app.
Configure your database connection.
What file contains your environment configurations?
What file references this configuration, and sometimes requires manual overrides?
Use php artisan tinker to verify your database connection. An easy way to go about this, while familiarizing yourself with Laravel's Connection class, is to create a table; insert a record into it; and then drop the table.

Use the database documentation to figure out how to do this.
Use Artisan to set up user authentication.

Which Artisan command do you use to accomplish this?
Hint: Read the docs, and check the output from php artisan for anything about authentication.
Scaffolding authentication creates some database tables. What command do you use to integrate these properly?
Serve the app and create a test user to ensure everything is hooked up correctly.
From here, you'll build out the primary functionality of your application.

Walkthrough

Milestone 1 // Meals

Create a Meal model.
Make sure your Meal model allows users to add a name.
Create your Meals controller and hook it up in routes.php
Hint: This takes very little code.
Make sure unauthenticated users can't access Meal routes!
Add a form that allows users to create a meal.
What method serves the form to create a meal?
What method handles the submission?
Where is the best place to redirect a user after creating a meal?
Create a page to display meal details.
We want to know when the meal was entered, but the timestamp isn't human readable. Fix this. Hint: Check the docs, or use PHP's format method directly.
Milestone 2 // Foods

On the meal detail page, create a form that allows users to add foods.
After you've wired up the backend, use Bootstrap to prettify your forms to make things look pretty.
Create the Food model and controller that will allow us to actually implement this.
What is the relationship between a Food and a Meal? Update your code to reflect this relationship.
Wire the Create Food form up to your FoodsController. Consider the following:
You'll need to make a change in your routes.php.
What controller(s) handles this update?
Refer to the documentation for help.
Make sure you can see a Meal's foods on the detail page.
If there are no foods, let the user know Hint: Blade has if statements.
Add information to the Meals detail page, like total calories in the meal, total macronutrients, etc.
How would you get this information, and where would you place your methods?
Milestone 3 // Validations

Take a moment to ensure that users can't enter meals without names, or foods without names and macronutrient data.
Validate both on the frontend, with HTML5 input attributes, and on the backend.
If you'd like, you can only require food names, and default food macronutrient values to 0.
Be sure to refer to the documentation!
Milestone 3 // Homepage

Build out the following in your HomeController.

Display earliest meals first (i.e., breakfast, then lunch, then dinner).
What relation does this imply?
Where will you need to update your routes?
Display the user's meals for the day, or a notification that they haven't eaten anything and a link for adding meals.
Where should you be retrieving today's meals?
The query isn't trivial. Refer to this blog post for a how-to. Hint: Use the Carbon method. But, be sure to require the Carbon class!
Add an 'All Meals' link to the navbar, and report every meal a user has ever saved.
Don't worry about prettifying this just yet; dump the data into a list for now.
Redirect all requests coming from an authenticated user to the welcome route to this dashboard.
In other words, unauthenticated users should see the landing page. Authenticated users should always be redirected to the dashboard if they try to hit the landing page.
BONUS

Present the user's macronutrient and calorie totals on the homepage. If the user's calorie total is above their calorie threshold for the day, color it red.
