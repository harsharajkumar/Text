#Text Analysis and Cleaning Library
This Python library provides tools for analyzing and cleaning text data. The library includes classes and methods to count various text components, extract specific elements, clean unwanted parts, and perform basic text processing on a DataFrame.

Features
Counter Class
Count Words: Counts the number of words in the text.
Count Characters: Returns the number of characters in the text.
Count Average Word Length: Calculates the average word length in the text.
Count Stopwords: Counts the number of stopwords present in the text.
Count Hashtags: Counts the number of hashtags in the text.
Count Mentions: Counts the number of mentions (words starting with @).
Count Digits: Counts the number of digits in the text.
Count Uppercase Words: Counts the number of words in uppercase.
Count Whitespace: Counts the number of whitespace characters.
Count Vowels and Consonants: Counts the number of vowels and consonants.
Count Emails, URLs, Special Characters, Phone Numbers, HTML Tags: Provides methods to count the occurrences of these elements in the text.
Extractor Class
Get Stopwords: Extracts and returns stopwords from the text.
Get Sentence and Word Tokens: Returns sentence and word tokens.
Get Hashtags, Mentions, Digits, Uppercase Words: Returns lists of these elements from the text.
Get Emails, URLs, Phone Numbers, HTML Tags: Extracts these elements and returns them as lists.
Get Repeated Words: Returns a list of the most repeated words and their frequency.
Correct Spelling: Corrects the misspelled words in the text.
Get Sentiment: Analyzes and returns the sentiment of the text.
Cleaner Class
Remove Stopwords, Digits, Emails, URLs, Special Characters, HTML Tags, Accented Characters, Emojis: Removes these elements from the text.
Remove Abbreviations: Replaces abbreviation words with their full forms.
Remove Duplicate Words: Removes duplicate words from the text.
Stemming and Lemmatization: Reduces words to their base or root form.
Quick Clean: A one-stop function to clean text by removing specific elements and applying stemming or lemmatization.
Dataframe Class
Word Frequency Count: Returns word frequency counts from a DataFrame column.
Convert to Vectors: Converts text into vectors using CountVectorizer or TfidfVectorizer.
Clean DataFrame: Cleans text in a DataFrame column by applying the cleaning methods in the Cleaner class.
Installation
bash
Copy code
pip install -r requirements.txt
Ensure you have the necessary dependencies installed as specified in requirements.txt.

Usage
python
Copy code
from text_analysis import Counter, Extractor, Cleaner, Dataframe

# Example usage
text = "Sample text with #hashtag and @mention. Visit https://example.com for more info. Email: test@example.com"

# Counter Example
counter = Counter(text=text)
print(counter.count_words())

# Extractor Example
extractor = Extractor(text=text)
print(extractor.get_hashtags())

# Cleaner Example
cleaner = Cleaner(text=text)
print(cleaner.remove_urls())

# Dataframe Example
df = pd.DataFrame({'text': [text, "Another text"]})
dataframe = Dataframe(df=df, col='text')
cleaned_corpus = dataframe.clean(remove_complete=True, make_base='stemming')
print(cleaned_corpus)
Contributing
Feel free to submit pull requests, report issues, or suggest features.

