# Wikipedia Tooltips for Anki
An Anki addon that automatically adds Wikipedia tooltips to medical terms in your cards.

## How it Works
When reviewing cards, this addon:
1. Scans the answer text for medical terms and terminology
2. Queries Wikipedia for definitions of those terms
3. Adds interactive tooltips that show the Wikipedia summary and image when hovering
4. Saves results in a cache to avoid repeated API calls

## Features
- **Automatic Term Detection**: Intelligently identifies medical terms and phrases in your card content
- **Rich Tooltips**: Shows Wikipedia summary text and thumbnail image in the tooltip 
- **Smart Filtering**: Avoids common words and non-medical terms using built-in block lists
- **Click-through**: Links to full Wikipedia articles for more details
- **Performance Optimized**:
  - Caches Wikipedia results
  - Batches API requests (max 50 concurrent)
  - Only processes new/changed content

## Usage
The addon works automatically - just review cards normally and hover over underlined terms to see definitions.

Terms are detected in three ways:
- Single words (unigrams)
- Two word phrases (bigrams) 
- Three word phrases (trigrams)

The addon intelligently filters out common words and only queries Wikipedia for likely medical terms.

## Configuration
You can customize which terms are blocked by editing the `BLOCKED_WORDS` and `BLOCKED_UNIGRAMS` arrays in `web.js`.

## Technical Details
- Uses Wikipedia's REST API to fetch summaries 
- Tooltip UI built with Tippy.js
- MutationObserver watches for card content changes
- Handles HTML sanitization and entity decoding
- Prevents tooltip nesting/overlapping

## Support
Created by William Guy. For issues and feature requests, please file an issue on GitHub.

## License 
MIT License - feel free to modify and reuse with attribution.
