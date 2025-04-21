# Wikipedia Tooltips for Anki
An Anki addon that automatically adds Wikipedia tooltips to medical terms in your cards.

![alt text](https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Demo.png "Ankipedia Demo Image")

## Overview 

### How it Works
When reviewing cards, this addon:
1. Scans any fields with the class 'ankipedia' 
3. Queries Wikipedia for definitions of terms within fields with that class
4. Adds interactive tooltips that show the Wikipedia summary and image of those terms hovering
5. Saves results in a cache to avoid repeated API calls

### Usage
The addon works automatically - just review cards normally and hover over underlined terms to see definitions.

Terms are detected in three ways:
- Single words (unigrams)
- Two word phrases (bigrams) 
- Three word phrases (trigrams)
- Four word phrases and longer are excluded to reduce calls to the Wikipedia API

## Configuration

### 1. How to Set Up Your Cards:
In Anki, go to your card template
In the front or back template, wrap the field you want to include with the class "ankipedia" (see below). When this field is visible on your screen the script that calls the Wikipedia tooltips will run. If you want it on the front and back of your cards you will need to add the class to both sides of the cards – similarly, you will need to add it to any different card types you also want to include.

![alt text](https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Installation.png "Ankipedia Demo Image")

### 2. Blocked Words
You can customize which terms are blocked by editing the `BLOCKED_WORDS` and `BLOCKED_UNIGRAMS` arrays in `web.js`. This code includes comments explaining when to use each list as they both apply rules slightly differently.

### 3. Tips
You can add the .ankipedia class to multiple fields if needed
The class is case sensitive, so use lower case 'ankipedia'
The addon will only process new content when it changes
The div can contain any Anki field or HTML content
This setup requirement ensures the addon only processes relevant card content and avoids scanning the entire page unnecessarily.

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
