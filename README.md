# UG-Ripper

**UG-Ripper** is a web scraper designed to automate the process of downloading guitar tabs from Ultimate Guitar. It uses Selenium for web automation and BeautifulSoup for parsing HTML content. The program logs into Ultimate Guitar using user-provided credentials, navigates to a specified playlist, and downloads the guitar tabs as PDF files using pdfkit. The download location and other configurations are specified in a configuration file `config.ini`. The program handles login failures and timeouts gracefully, logging any errors encountered during the scraping process.

<span style="color: red;">**Note: The scraper currently does not work with pro tabs.**</span>

## Features
- Automated login to Ultimate Guitar
- Navigate to a specified playlist
- Download guitar tabs as PDF files
- Configurable download location
- Error handling and logging

## Installation

### Prerequisites
- **Python 3.6+**: Ensure you have Python installed. You can download it from [python.org](https://www.python.org/).
- **pip**: Ensure you have pip installed and updated. You can do both by running:
  ```sh
  python -m ensurepip --upgrade
  ```
- **wkhtmltopdf**: Download and install wkhtmltopdf from [wkhtmltopdf.org](https://wkhtmltopdf.org/). Make sure to note the path to the wkhtmltopdf executable.

### Python Dependencies
Install the required Python packages using pip:
```sh
pip install selenium beautifulsoup4 pdfkit
```
- **selenium**: A web automation tool used to control web browsers through programs and perform browser automation.
- **beautifulsoup4**: A library for parsing HTML and XML documents, used for web scraping purposes to extract data from web pages.
- **pdfkit**: A python wrapper for wkhtmltopdf that allows for the creation of PDF files from HTML content, used to convert the scraped guitar tabs into PDF format.

### WebDriver
Download the appropriate WebDriver for your browser. For Firefox, you can download the GeckoDriver from [mozilla/geckodriver](https://github.com/mozilla/geckodriver). Ensure the WebDriver is in your system's PATH.

### Configuration
Configuration File: Copy the `config-template.ini` to `config.ini` and fill in the required details.

```ini
[URLs]
login_url = https://www.ultimate-guitar.com/
playlist_url = https://www.ultimate-guitar.com/user/playlist/view?id=

[Download]
location = ./DLs

[PDFKit]
executable_path = /path/to/wkhtmltopdf

# [Authentication]
# username = your_username
# password = your_password
```

Authentication: You can either provide your Ultimate Guitar credentials in the `config.ini` file under the `[Authentication]` section or let the script prompt you for credentials at runtime.

## Running UG-Ripper
Run the script using Python:
```sh
python ug-ripper.py
```

The script will log in to Ultimate Guitar, navigate to the specified playlist, and download the guitar tabs as PDF files to the configured download location.

## Logging
The script logs its activities, including any errors encountered during the scraping process. Logs are printed to the console.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Author
MonJhod - GitHub

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any improvements or bug fixes.

## Acknowledgments
- Selenium
- BeautifulSoup
- pdfkit
- wkhtmltopdf

Feel free to reach out with any questions or issues. Happy scraping!

## Disclaimer
This project is not affiliated with Ultimate Guitar Tabs in any way.