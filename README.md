# CS208: My Simple TODO App

Developer: Gavin Dombrowsky

GitHub: (https://github.com/gavindombrowsky/12.03-Lab---Full-Stack?tab=readme-ov-file)

# Project Overview

This is a full-stack web app I built for my CS208 course. While it looks like a simple task manager, it’s a fully functional CRUD (Create, Read, Update, Delete) application. Unlike a standard list that resets when you refresh the page, this app is backed by a MariaDB database, so your tasks actually stick around.
What it can do:

    Everything is stored in a real database, not just your browser.

    You can click and change a task description directly in the list.

    A simple checkbox toggles tasks between "Not Completed" and "Completed."

   I added validation so you can't submit a blank task by accident.

   Custom CSS makes the UI clean and easy to use on different screen sizes.

# How to Get Started
1. Set up the Database

First, you’ll need to prep your environment. Run this script to install MariaDB and get the server running (you only need to do this once):
Bash

./setup_scripts/install_db.sh

2. Create the Tables

Next, we need to set up the actual "folders" for our data. This command creates the todos table and adds some starter data:
Bash

sudo mysql -u root -p < ./setup_scripts/create_demo_table.sql

3. Install Dependencies & Run

Finally, grab the necessary Node.js packages and fire up the app:
Bash

npm install
npm start

The app runs on port 3000. If you're in Codespaces, it should give you a "Open in Browser" pop-up automatically!

# The Frontend and the Backend

    Frontend: Built with Pug templates and custom CSS3.

    Backend: Powered by Node.js and Express.

    Database: MariaDB (MySQL) manages the data.

    Logic: I used custom middleware in bin/db.js to keep the database connection smooth.

What I worked on:

To get this app to where it is now, I made several key updates:

    routes/index.js: Created the logic for the /update/:id route so the database knows when you change a task.

    views/index.pug: Transformed the static display into a dynamic form with interactive checkboxes and text fields.

    public/stylesheets/style.css: Spiced up the design with better spacing, hover states, and a strikethrough effect for finished tasks.

# Troubleshooting

Having trouble connecting? Try these three things:

    Restart the DB: Run the install_db.sh script again to make sure the service is active.

    Check Credentials: Double-check bin/db.js to ensure the app has the right permissions to talk to the database.

    Verify Tables: Hop into the MySQL CLI and run DESCRIBE todos; to make sure the table exists.