# Ankipedia – Wikipedia Tooltips in Anki
Ankipedia is an Anki addon that adds helpful Wikipedia pop-ups to terms in your flashcards, making it easy to understand unfamiliar concepts while you study. Just hover over underlined words during reviews to see short definitions and images — no extra clicks or effort needed.
<br><br>
<table>
  <tr>
    <td colspan="3">
      <img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Demo-2.png" alt="Ankipedia Demo Image 2" style="width: 100%; height: auto;">
    </td>
  </tr>
  <tr>
    <td><img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Demo-1.png" alt="Ankipedia Demo Image 1" style="width: 100%; height: auto;"></td>
    <td><img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Demo-3.png" alt="Ankipedia Demo Image 3" style="width: 100%; height: auto;"></td>
    <td><img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Demo-4.png" alt="Ankipedia Demo Image 4" style="width: 100%; height: auto;"></td>
  </tr>
</table>

<i>Screenshots demonstrating the Ankipedia base display, tooltips, theme options and word/unigram deletions.</i>
<br><br>

## Overview 

### How it Works
When reviewing cards, this addon:
1. Scans card content based on your configuration
2. Takes the content and queries Wikipedia for relevant pages
3. Adds interactive tooltips showing Wikipedia summaries and images when hovering
4. Saves results in a cache to avoid repeated API calls

### Usage
The addon works automatically - just review cards normally and hover over underlined terms to see definitions. The queries to Wikipedia take a few seconds, a short card (<50 words) should get responses within one second, longer cards (50 to 150 words) will take a few seconds.

Terms are detected in three ways:
- Single words (unigrams)
- Two word phrases (bigrams) 
- Three word phrases (trigrams)
- Four word phrases and longer are excluded to reduce calls to the Wikipedia API

You can also right-click any underlined term to:
- Copy the term text
- Add to Blocked Words (blocks the term and any phrases containing it)  
- Add to Blocked Unigrams (only blocks the exact term when it appears alone)

## Configuration

### 1. Accessing Options
1. Open Anki
2. Go to Tools > Ankipedia Options
3. Configure your preferences across 4 tabs:

#### Setup
- Wikipedia Language: Choose which language version of Wikipedia to query (currently the top-45 Wikipedia languages are included
- Class Name: Control which elements get tooltips (e.g. 'card' for all content)

#### Appearance  
- Theme: Light, Dark or Auto theme for tooltips
- Term Border Style: Solid, Dotted or None
- Underline Thickness: Adjust from 1-3px
- Underline Color: Customize the underline color
- Tooltip Button Colors: Customize background and text colors

#### Blocked Words
- Blocked Words: Terms that will never show tooltips (includes phrases containing these words)
- Blocked Unigrams: Single words that won't show tooltips when they appear alone

#### About
Information about the addon and links to resources

### 2. Setting Up Your Cards
1. Choose where you want tooltips to appear:
   - For all card content: Set Class Name to 'card' in options
   - For specific fields: Add your chosen class name to those field wrappers
   - You can use any valid HTML class name

### 3. Tips
- You can apply tooltips to multiple areas by using the same class name
- The addon will only process new content when it changes
- Class names are case sensitive
- The class can be added to any element containing text
- Highlight and right-click terms to quickly add them to blocked lists
- Use the appearance tab to match your card styling

<table>
  <tr>
    <td><img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Settings-1.png" alt="Ankipedia Settings" style="min-width:400px; width:100%; height:auto;"></td>
    <td><img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Settings-2.png" alt="Ankipedia Settings" style="min-width:400px; width:100%; height:auto;"></td>
    <td><img src="https://github.com/ctrlaltwill/Ankipedia/blob/main/Images/Settings-3.png" alt="Ankipedia Settings" style="min-width:400px; width:100%; height:auto;"></td>
  </tr>
</table>
<i>Screenshots demonstrating the Ankipedia setup and some of the customisation features.</i>


## More Details 

### Technical Details
- Uses Wikipedia's REST API to fetch summaries 
- Tooltip UI built with Tippy.js
- MutationObserver watches for card content changes
- Handles HTML sanitization and entity decoding

### Support
Created by William Guy. For issues and feature requests, please file an issue on GitHub.

If you find this addon helpful, consider supporting development:

<a href="https://www.buymeacoffee.com/williamguy" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

## Acknowledgements

### Wikipedia
Content accessed through Wikipedia's API is licensed under [Creative Commons Attribution-ShareAlike 3.0](https://creativecommons.org/licenses/by-sa/3.0/). Wikipedia® is a registered trademark of the Wikimedia Foundation, Inc.

## License

This addon is licensed under the GNU General Public License v3.0.
