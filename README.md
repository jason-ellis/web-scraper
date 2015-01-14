# Web Scraper

A web scraper that uses input from CSV files placed in the same directory as the
application. Outputs a CSV file with results.

This web scraper has a specific purpose to search a div with id HLMFfooter for strings that the input CSV file specifies. This is to check for a specific issue where HTML is generated with errors in production environment.

I created this program to automate checking 500+ sites on a weekly basis. This was done for a previous job, so the code has been intentionally obfuscated.

All CSV files are separated by line breaks, one value per line, no quotes.
url.csv file is used to obfuscate site I'm searching for privacy reasons.
input.csv and idNames are required because sites are formatted as:
https://xxx.xxx.com/_unique_id_/yyyy

Required files:
- url.csv - The URL to scan. For intended purpose, this app uses a URL on line 1, appends the path from identifier.csv, and then (optionally) appends the 2nd line from url.csv.
- input.csv - List of identifiers/paths concatenated to URL in url.csv.
- checklist.csv - List of strings to search for and return PASS if they are not present, FAIL if they are present.
- output.csv - Results of scraping are printed to this file
