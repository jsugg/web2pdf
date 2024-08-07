![Web2PDF logo](.github/assets/web2pdf-logo.png)

# Web2PDF

Web2PDF is a robust web scraper designed to recursively navigate websites starting from a given base URL and convert the pages to PDF files using Playwright.

It offers high configurability, allowing you to specify parameters such as the maximum depth of recursion, page size for PDFs, delay between requests, number of retries for failed requests, and the degree of concurrency.

The module includes comprehensive error handling, logging, and signal handling mechanisms to gracefully shut down the scraping process if interrupted. Additionally, Web2PDF supports converting Jupyter Notebooks to PDFs.

## Features

- **Recursive Web Scraping**: Navigate through web pages starting from a base URL.
- **PDF Conversion**: Convert web pages to PDF files using Playwright.
- **High Configurability**: Set maximum depth, page size, delay, retries, concurrency, and allowed high-level domains for scraping.
- **Jupyter Notebook Support**: Convert Jupyter Notebooks to PDFs.
- **Robust Error Handling**: Comprehensive error and signal handling for smooth operation.
- **Logging**: Detailed logging to monitor the scraping process.

## Usage

### Basic Usage
```sh
./web2pdf https://example.com
```

### Specify Output Directory and Maximum Depth
```sh
./web2pdf --output-dir "output" --depth 3 https://example.com
```

### Customize Page Size and Delay Between Requests
```sh
./web2pdf --page-size Letter --delay 2 https://example.com
```

### Enable Verbose Logging
```sh
./web2pdf --verbose https://example.com
```

### Advanced Example
```sh
./web2pdf --depth 2 --verbose --delay 1 --retries 3 --concurrency 20 --only github.io https://langchain-ai.github.io/langgraphjs/
```

## CLI Flags

| Flag          | Description                                                                                  | Default Value |
|---------------|----------------------------------------------------------------------------------------------|---------------|
| `url`         | The base URL of the website to scrape.                                                       |               |
| `--output-dir`| The directory to save PDFs.                                                                  | `pdfs`        |
| `--depth`     | The maximum depth of recursion for scraping.                                                 | `2`           |
| `--page-size` | The page size for the PDFs (e.g., A4, Letter, Legal, etc.).                                               | `A4`          |
| `--delay`     | The delay in seconds between requests.                                                       | `1.0`         |
| `--retries`   | The number of retries for failed requests.                                                   | `3`           |
| `--concurrency`| The number of concurrent requests to execute.                                               | `4`           |
| `--max-pages` | The maximum number of pages to scrape.                                                       | `100`         |
| `--verbose`   | Enable verbose logging.                                                                      | `False`       |
| `--timeout`   | Timeout for page navigation in milliseconds.                                                 | `60000`       |
| `--only`      | Comma-separated list of allowed high-level domains for scraping.                             | `''`          |

## Installation

To install the required dependencies, run:
```sh
pip install -r requirements.txt
```

Install additional dependeencies:

For MacOS:
```sh
brew install gs
brew install inkscape
```

For Linux:
```sh
sudo apt-get install gs
sudo apt-get install inkscape
```

For Windows (WLS):
```sh
sudo apt install gs
sudo apt install inkscape
```

Ensure that `web2pdf` has execute permissions. If you are unsure, run:
```sh
chmod +x web2pdf
```

## Contributing

We welcome contributions! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Make your changes.
4. Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the [MIT License](LICENSE).
