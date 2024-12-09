**Overview**
This project performs comprehensive analysis on YouTube comments from the CR7 channel. It involves collecting, processing, and analyzing data to uncover insights using Natural Language Processing (NLP) techniques.

**Features**
Data Collection: Fetches video data and comments using the YouTube API.
Data Storage: Stores data in MongoDB for easy access and manipulation.
Streaming: Streams comments to Kafka for real-time processing.
Sentiment Analysis: Uses VADER and TextBlob to determine the sentiment of comments.
Visualization: Compares sentiment distributions and model agreements.

**Technologies Used**
Languages: Python
Libraries: Kafka, MongoDB, VADER, TextBlob, Matplotlib, and TQDM
APIs: YouTube Data API

**Setting Up the API Key**
To use the YouTube Data API, you need to set up your API key securely:

Obtain Your API Key:
Go to the Google Cloud Console.
Create a new project or select an existing one.
Enable the YouTube Data API v3 for your project.
Generate an API key under the "Credentials" section.
Store the API Key Securely:

Save the API key in a text file (e.g., cr7_yt.txt) to avoid exposing it in your code.
Place the text file in a secure location (e.g., C:\API\cr7_yt.txt).
Retrieve the API Key in Code:

Use the following function to load the API key in your python script:

def get_api_key(file_path):
    try:
        with open(file_path, "r") as file:
            return file.read().strip()
    except FileNotFoundError:
        print(f"Error: API key file not found at {file_path}")
        exit(1)
API_KEY_FILE = r"C:\API\cr7_yt.txt"
API_KEY = get_api_key(API_KEY_FILE)

This ensures the API key is not hardcoded in the script, protecting it from accidental exposure.


**Results**
Total Comments Analyzed: 873,805
Total English Comments Processed: 271,838
Sentiment Distribution:
TextBlob: Neutral (159,770), Positive (102,567), Negative (9,737)
VADER: Positive (134,187), Neutral (125,702), Negative (12,185)
