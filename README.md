# Lecture 6 Demo - Deploying to Heroku

This demo explains how to take a Github repository and deploy it to the world!

## Copy this repo to your own personal one
1. On https://github.com/new, create a new repository (personal, not owned by org) called `lect6`
2. In terminal, in your home directory, clone the repo:`git clone https://github.com/NJIT-CS490-SP21/lect6-demo-heroku.git`
3. `cd` into the repository that is created and you should see all the files now.
4. Then, connect this cloned repo to your new personal repo made in Step 1: `git remote set-url origin https://www.github.com/{your-username}/lect6` (be sure to change your username and remove the curly braces)
5. Run `git push origin main` to push the local repo to remote. You should now see this same code in your personal `lect6` repo.

## Sign up for New York Times Developer Account
1. Follow the instructions here: https://developer.nytimes.com/get-started (if email verification is showing errors, just refresh the page)
2. When creating a New App, make sure you enable Article Search API.

## Install Requirements (if you don't already have them)
1. `pip install python-dotenv`
2. `pip install requests`

## Setup
1. Create `.env` file in your project directory
2. Add your NYT key from https://developer.nytimes.com/my-apps with the line: `export NYT_KEY='YOUR_KEY'`
3. In `app.py`, change Line 13 to a topic you want to get news about!

## Run Application
1. Run command in terminal `python app.py`
2. Preview web page in browser '/'

## Deploy to Heroku
1. Install Heroku CLI: `npm install -g heroku`. This could take a few minutes. In the meantime...
2. Create a free account on Heroku https://signup.heroku.com/login
3. Create a `requirements.txt` file with all your non-standard dependencies (based on any libraries you are importing), separated by a newline. In our case, they are `Flask` w/ a capital F, `requests`, and `python-dotenv`. Note that libraries like `os` are standard imports, so they don't need to be included.
4. Create a `Procfile`, which has the command that Heroku will use to run your app: `web: python app.py` (see documentation https://devcenter.heroku.com/articles/getting-started-with-python#define-a-procfile)
5. Add + commit all changed files with git
6. Log in to Heroku: `heroku login -i`
5. Create a Heroku app: `heroku create`. This will create a new URL and associated host for you.
6. Push your code to Heroku: `git push heroku main`. This actually pushes your code to Heroku's remote repository.
7. Open your app with your new URL: `heroku open`. Click the link to open if it doesn't open on its own. It shouldn't work, because it doeesn't have any environment variables (remember, your `.env` file is not in your git repository!)
8. Go to https://dashboard.heroku.com/apps and click your App, then go to Settings, and click "Reveal Config Vars"
10. Add your secret key from `.env` with the matching variable name (`NYT_KEY`) and value (your key, without quotation marks!)
11. Run `heroku open` or refresh the URL if you have it open. Voila!
