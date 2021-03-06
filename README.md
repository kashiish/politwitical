# Politwitical

Politwitical is a simple web app created using `Flask`, `tweepy`, and `textblob` that displays the most tweeted political words/hashtags at the current moment in time. 

AJAX requests are made every 30 seconds to get data from `Flask`. `Flask` collects tweets for 30 seconds using Twitter's Streaming API and filters tweets based on user (politicians, political twitter accounts, news accounts, etc). The tweets are then processed, their polarity is determined using `textblob`, and the frequencies of all the important words are calculated. All this data is stored in a Python dictionary and translated into a JSON object which is sent to Javascript using `Flask Response`. Javascript then displays the words on the screen and creates a pie chart (using `Chart.js`) for each word that presents the number of positive, neutral, and negative tweets that contain the specific word.

### Installation

If you would like to run the app on your local server, please clone the repository and sign up for a Twitter developer account. In your developer account, create an 
application to get the API keys and tokens. Next, you will need to create a file called ```private.py``` in the project's directory and add the the following:

```
CONSUMER_KEY = "your consumer key (API Key)"
CONSUMER_SECRET = "your consumer secret (API Secret)"
ACCESS_TOKEN = "your access token"
ACCESS_TOKEN_SECRET = "your access token secret"
```
In your command line type:

```
pip install -r requirements.txt
```

Next, change to the project's directory and type:
```
python app.py
```

Now, you should be able to run the app by visiting http://localhost:5000.


### Bugs + Features

- Overlapping words and charts (JavaScript)
- Filtering, processing, and analyzing the tweets is a pretty slow process (Python)


### Other

Please feel free to add more users in ```filter_users.py``` or add more words to any of the lists in ```settings.py```. Also feel free to fix/report any bugs you may find.





