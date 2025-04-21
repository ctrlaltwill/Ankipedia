# Wikipedia Tooltips for Anki
An Anki addon that automatically adds Wikipedia tooltips to terms in your cards.

![alt text](https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Demo.png "Ankipedia Demo Image")

## Overview 

### How it Works
When reviewing cards, this addon:
1. Scans any fields with the class 'ankipedia' 
3. Takes the content from those fields and queries Wikipedia for pages on that content
4. Adds interactive tooltips that show the Wikipedia summary and image of those terms when hovering (if content is found)
5. Saves results in a cache to avoid repeated API calls

### Usage
The addon works automatically - just review cards normally and hover over underlined terms to see definitions. The queries to Wikipedia take a few seconds, a short card (<50 words) should get responses within one second, longer cards (50 to 150 words) will take a few seconds.

Terms are detected in three ways:
- Single words (unigrams)
- Two word phrases (bigrams) 
- Three word phrases (trigrams)
- Four word phrases and longer are excluded to reduce calls to the Wikipedia API

## Configuration

### 1. How to Set Up Your Cards:
In Anki, go to your card template and in the front or back template (or both), wrap the field you want to include with the class "ankipedia" (there is an example image below of this). When this field is visible on your screen the script that calls the Wikipedia tooltips will run. If you want it on the front and back of your cards you will need to add the class to both sides of the cards – similarly, you will need to add it to any different card types you also want to include.

![alt text](https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Installation.png "Ankipedia Demo Image")

### 2. Blocked Words
You can customize which terms are blocked by editing the `BLOCKED_WORDS` and `BLOCKED_UNIGRAMS` arrays in `web.js`. This code includes comments explaining when to use each list as they both apply rules slightly differently. In the future I would like to update this list to be a plain text file separate outside the main plugin script, but this is how it is currently!

### 3. Tips
- You can add the .ankipedia class to multiple fields if needed
- The class is case sensitive, so use lower case 'ankipedia'
- The addon will only process new content when it changes
- The div can contain any Anki field or HTML content

## More Details 

### Technical Details
- Uses Wikipedia's REST API to fetch summaries 
- Tooltip UI built with Tippy.js
- MutationObserver watches for card content changes
- Handles HTML sanitization and entity decoding
- Prevents tooltip nesting/overlapping

### Support
Created by William Guy. For issues and feature requests, please file an issue on GitHub.

### License 
MIT License - feel free to modify and reuse with attribution.

![alt text](https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Ankipedia_Demo.gif "Ankipedia Demo Animation")
