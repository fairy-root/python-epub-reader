# Python CLI EPUB Reader

Python CLI Epub reader with page navigation, bookmarks management, search management, save pages and book to text files and reading sessions to save and load your current progress

## Features

- Scans and lists EPUB files in the script directory
- Reads all HTML/XHTML pages in an EPUB file
- Extracts and displays title and author from EPUB metadata, and lists them as choices for the user to start reading the contents of the EPUB file
- Cleans and displays text content
- Allows navigation through pages with "n" (next), "p" (previous), "sp" (save page), "sb" (save book), "q" (quit), "j" (jump to page), "jp" (jump to percentage), "jb" (jump to bookmark), "db" (delete bookmark), "dab" (delete all bookmarks), "sh" (view search history), "ds" (delete search history), "das" (delete all search history), "al" (adjust lines per screen)
- Enhanced page lines depending on punctuation rather than HTML tags
- Save a page or the whole EPUB text to a text file `.txt`
- Saves reading session including current page, progress, bookmarks, and search history, and loading them so you never lose your progress.
- Colorized output for enhanced readability
- Graceful exit using `CTRL+C`
- Minimal dependencies
- Error handling

## Usage

1. **Clone the repository:**

   ```sh
   git clone https://github.com/fairy-root/python-pub-reader.git
   cd python-epub-reader
   ```

2. **Install dependencies:**

   ```sh
   pip install beautifulsoup4
   ```

3. **Run the script:**

   ```sh
   python epub.py
   ```

4. **Follow the prompts to select an EPUB file and navigate through its pages.**

## Script Functions

### `epub.py`

The script contains the following functionalities:

- **Print Colored Text:**
  - `print_colored(text: str, color: str) -> None`: Prints text in specified color.
  - `input_colored(prompt: str, color: str) -> str`: Gets user input with colored prompt.

- **EPUB Reading:**
  - `read_epub_metadata(epub_path: str) -> Tuple[str, str, str, str]`: Reads the title, author, publication date, and language from the EPUB metadata.
  - `read_epub_pages(epub_path: str) -> List[str]`: Reads all pages and returns cleaned text content.
  - `get_epub_files_with_metadata(directory: str) -> List[Tuple[str, str, str, int, str, str]]`: Returns a list of EPUB files with their metadata and page counts.
  - `display_choices(epub_files_with_metadata: List[Tuple[str, str, str, int, str, str]]) -> str`: Displays available EPUB files with metadata and returns the user's choice.
  - `display_page(pages: List[str], page_number: int, line_offset: int = 0, lines_per_screen: int = 20) -> None`: Displays a specific page with pagination.
  - `save_page(pages: List[str], page_number: int, title: str, author: str) -> None`: Saves the current page to a text file.
  - `save_book(pages: List[str], title: str, author: str) -> None`: Saves the entire book to a text file.

- **Navigation and Bookmarks:**
  - `jump_to_page(pages: List[str]) -> int`: Prompts the user to jump to a specific page.
  - `jump_to_percentage(pages: List[str]) -> Tuple[int, int]`: Prompts the user to jump to a specific percentage within a page.
  - `add_bookmark(bookmarks: List[Tuple[int, float]], page_number: int, progress: float) -> None`: Adds a bookmark at the current position.
  - `display_bookmarks(bookmarks: List[Tuple[int, float]]) -> None`: Displays all bookmarks.

- **Search History:**
  - `search_text(pages: List[str], query: str) -> List[Tuple[int, str]]`: Searches for text within the book and returns matching sentences.

- **Reading Session:**
  - `save_reading_session(book_id: str, page_number: int, line_offset: int, progress: float, bookmarks: List[Tuple[int, float]], search_history: List[str]) -> None`: Saves the current reading session.
  - `load_reading_session(book_id: str) -> Tuple[int, int, float, List[Tuple[int, float]], List[str]]`: Loads the saved reading session.

- **Global Settings:**
  - `load_global_settings() -> Dict`: Loads the global settings from a JSON file.
  - `save_global_settings(settings: Dict) -> None`: Saves the global settings to a JSON file.

- **Main Function:**
  - `main()`: Handles EPUB file reading, page navigation, saving pages or the whole book, managing bookmarks, search history, and user interactions.

## Donation

Your support is appreciated:

- USDt (TRC20): `TGCVbSSJbwL5nyXqMuKY839LJ5q5ygn2uS`
- BTC: `13GS1ixn2uQAmFQkte6qA5p1MQtMXre6MT`
- ETH (ERC20): `0xdbc7a7dafbb333773a5866ccf7a74da15ee654cc`
- LTC: `Ldb6SDxUMEdYQQfRhSA3zi4dCUtfUdsPou`

## Contributing

Contributions are welcome! If you have suggestions for improvements or find any issues, please open an issue or create a pull request.

### Steps to Contribute

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Make your changes.
4. Commit your changes: `git commit -m 'Add some feature'`
5. Push to the branch: `git push origin feature/your-feature-name`
6. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

- [GitHub: FairyRoot](https://github.com/fairy-root)
- [Telegram: @FairyRoot](https://t.me/FairyRoot)