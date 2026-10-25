# Reddit Analyzer

A Flask web app that scrapes a subreddit, runs sentiment analysis on its posts, and turns the results into charts: when people post, which posts score well, and which words dominate the conversation.

Term project for MIS3640 (Problem Solving & Software Design) at Babson College, Fall 2018.

![Search page](images/Main_page_2.PNG)

## What it does

1. Pick a subreddit, a sort order (top, hot, new, controversial…), a time period and how many posts to pull (up to 1,000).
2. The app collects the posts with PRAW and scores each title for sentiment with NLTK's VADER.
3. It generates an analysis page with a posting-time heatmap, score and comment distributions, sentiment-vs-score scatterplots and a word cloud.

![Heatmap](images/analysis_heatmap.PNG)
![Word cloud](images/analysis_wordmap.PNG)
![Score vs. sentiment](images/analysis_scatterplot.PNG)

A sample analysis from an included dataset is under the **Analysis** tab, so you can see the output without Reddit credentials.

## Running it locally

The old online demo was hosted on Heroku's free tier, which no longer exists, so the app now runs locally only.

1. Install the dependencies: `pip install -r requirements.txt`. The pinned versions are from 2018, so a fresh virtual environment is recommended, and some packages may need newer versions.
2. Create a Reddit "script" app at reddit.com/prefs/apps and set these environment variables, or put them in a `.env` file:
   client_id, client_secret, reddit_username, reddit_password, user_agent
3. From the project folder, run: `flask --app reddit_analyzer run --debug`
4. Open http://127.0.0.1:5000

## Tech

Python · Flask · PRAW · pandas · NLTK (VADER) · matplotlib · seaborn · wordcloud

The full project write-up is in `Term Project Ha Min Ko.docx`.
