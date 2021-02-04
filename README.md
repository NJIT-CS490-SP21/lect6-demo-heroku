# Lecture 6 Demo - Deploying to Heroku

This demo explains how to take a Github repository and deploy it to the world!

## Copy this repo to your own personal one
1. On https://github.com/new, create a new repository (personal, not owned by org) called `lect6`
2. In terminal, clone the repo:`git clone https://github.com/NJIT-CS490-SP21/lect6-demo-heroku.git`
3. `cd` into the repository and you should see all the files now.
4. Then, connect this repo to your personal repo from Step 1: `git remote set-url origin https://www.github.com/[your-username]/lect6` (be sure to change your username)
5. Run `git push origin main` to push the local repo to remote.

## Sign up for New York Times Developer Account
1. Follow the instructions here: https://developer.nytimes.com/get-started

## Install Requirements
1. `pip install python-dotenv`
2. `pip install requests`

## Setup
1. Create `.env` file in your main directory
2. Add your NYT key from https://developer.nytimes.com/my-apps with the line: `export NYT_KEY='YOUR_KEY'`
3. In `app.py`, change Line 13 to a topic you want to get news about!

## Run Application
1. Run command in terminal `python app.py`
2. Preview web page in browser '/'

## Deploy to Heroku
1. Install Heroku CLI: `npm install -g heroku`. This could take a few minutes. In the meantime...
2. Create a free account on Heroku https://signup.heroku.com/login
3. Create a `requirements.txt` file with all your dependencies (`Flask` w/ a capital F, `requests`, `python-dotenv`)
4. Create a `Procfile` with the command needed to run your app: https://devcenter.heroku.com/articles/getting-started-with-python#define-a-procfile
5. Add + commit all changed files with git
6. Log in to Heroku: `heroku login -i`
5. Create a Heroku app: `heroku create`
6. Push your code to Heroku: `git push heroku main`
7. Open your app on the INTERNET (it won't work yet): `heroku open`
8. Go to https://dashboard.heroku.com/apps and click your App, then go to Settings, and click "Reveal Config Vars"
10. Add your secret key from `.env` with the matching variable name (`NYT_KEY`) and value (your key, without quotation marks!)
