    # Kanji Adventure - Interactive Learning Website

    This project is a simple, interactive website designed to help users learn Japanese Kanji characters. It focuses on visual presentation and basic interaction, loading data from an external JSON file.

    ## Features

    * Displays Kanji characters in a grid, sorted by frequency rank.
    * Clicking a Kanji opens a modal window with details:
        * Meaning
        * Frequency Rank
        * On'yomi and Kun'yomi readings
        * Mnemonic story (if available in data)
        * Radicals (if available in data)
        * Pronunciation button (currently uses Web Speech API)
        * Link to a YouTube search for the Kanji in use.
    * Loads Kanji data dynamically from `kanji-data.json`.
    * Styled using Tailwind CSS.

    ## How to Run

    1.  Ensure you have both `index.html` and `kanji-data.json` in the same folder.
    2.  Open the `index.html` file in your web browser.

    ## Data Format (`kanji-data.json`)

    The Kanji data is stored in `kanji-data.json` as an array of objects. Each object represents a Kanji and should follow this structure:

    ```json
    {
      "kanji": "字", // The Kanji character
      "frequencyRank": 100, // Numerical rank
      "meaning": "Character, Letter", // English meaning(s)
      "story": "A child (子) under a roof (宀) learning characters.", // Mnemonic story
      "radicals": [ // Array of radical objects
        { "char": "宀", "name": "roof" },
        { "char": "子", "name": "child" }
      ],
      "readings": { // Object containing readings
        "onyomi": "ジ", // Katakana
        "kunyomi": "あざ, あざな, -な" // Hiragana
      },
      "youtubeSearchTerm": "日本語 漢字 字" // Search term for YouTube link
      // --- Future Addition for Audio Files ---
      // "kunyomiAudioUrl": "[https://example.com/audio/aza.mp3](https://example.com/audio/aza.mp3)",
      // "onyomiAudioUrl": "[https://example.com/audio/ji.mp3](https://example.com/audio/ji.mp3)"
    }
    ```

    **Note on Pronunciation:** Currently, the "Pronounce" button uses the browser's built-in Web Speech API. To use pre-recorded audio files, you would need to:
    1. Host your audio files online.
    2. Add properties like `kunyomiAudioUrl` and `onyomiAudioUrl` to the objects in `kanji-data.json` with the correct URLs.
    3. Modify the `pronounceKanji` function in `index.html` to fetch and play these audio files instead of using `SpeechSynthesisUtterance`.

    ## Contributing Data

    To add more Kanji or improve existing entries, edit the `kanji-data.json` file, ensuring each entry follows the specified format.
    ```

to do:
add https://youglish.com/ to kanji.
add pictograph images
