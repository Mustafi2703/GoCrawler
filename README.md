# GoCrawler

GoCrawler is a simple concurrent web crawler written in Go. It crawls a given base URL, follows internal links up to a configurable concurrency and page limit, and prints a report of the internal links found.

## Usage

First, build the project:

```sh
go build -o crawler
```

Run the crawler with:

```sh
./crawler <baseURL> <maxConcurrency> <maxPages>
```

- `<baseURL>`: The starting URL to crawl (e.g., `https://blog.boot.dev`)
- `<maxConcurrency>`: Maximum number of concurrent requests (e.g., `5`)
- `<maxPages>`: Maximum number of pages to crawl (e.g., `100`)

Example:

```sh
./crawler https://blog.boot.dev 5 100
```

## Testing

To run all tests:

```sh
go test ./...
```

This will execute all unit tests in the project and report any failures.

## Project Structure

- `main.go`: Entry point and CLI handling.
- `configure.go`: Configuration and shared state.
- `crawl_page.go`: Core crawling logic.
- `normalize_url.go`: URL normalization helpers.
- `print_report.go`: Output formatting.
- `*_test.go`: Unit tests for core components.

## Requirements

- Go 1.18 or newer