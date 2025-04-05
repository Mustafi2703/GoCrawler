# GoCrawler

A concurrent web crawler written in Go that maps the connections between web pages.

## Description

This web crawler efficiently explores websites by following internal links, mapping out the site structure, and reporting on how pages are connected. It uses Go's concurrency features to crawl multiple pages simultaneously while respecting rate limits.

## Features

- **Concurrent crawling**: Uses goroutines and channels for efficient parallel processing
- **Depth control**: Limits crawling to a specified depth from the starting URL
- **Rate limiting**: Prevents overwhelming target servers with configurable request rates
- **Internal link focus**: Only follows links within the same domain
- **Detailed reporting**: Generates a sorted report showing the number of internal links to each page

## Installation
- Go 1.22.5 or later
- External packages:
  - `golang.org/x/net/html`: For HTML parsing
# Download dependencies
go mod download

# Clone the repository
git clone https://github.com/Mustafi2703/GoCrawler.git

# Build the project
go build

./GoCrawler <starting-url> <max-depth> <rate-limit>

Example:
./GoCrawler https://example.com 3 10

This will:

Start crawling from https://example.com
Crawl to a maximum depth of 3 pages from the starting point
Limit requests to approximately 10 per second

#How it works
1. The crawler starts at the specified URL
2. It extracts all internal links from the page
3. For each new link found, it queues it for crawling if within the depth limit
4. The process continues concurrently until all reachable pages within the depth limit are crawled
5. Finally, it generates a report showing how many internal links point to each page

#Project Structure
1. main.go: Entry point and command line interface
2. crawler.go: Main crawling logic and concurrency handling
3. parser.go: HTML parsing and link extraction
4. report.go: Reporting and output formatting

