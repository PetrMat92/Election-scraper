# Election-scraper
Engeto project #3: This script is designed to scrape election data from the 2017 Chamber of Deputies elections in the Czech Republic via the official election results website: https://volby.cz/pls/ps2017nss/ps3?xjazyk=CZ and store the data in a CSV file.

# Libraries
The script is written in Python and uses the following libraries:

Requests, BeautifulSoup, Argparse, Re, CSV, OS,

# Features

URL Validation: The script validates the URL using the requests library to ensure that it is a valid URL.

Command Line Argument Validation: The script validates the command line arguments and returns the URL and file name as a tuple. The URL must start with https://www.volby.cz/pls/ps2017nss/ and the file name must have a .csv extension.

City Names Scraper: The script uses the city_names_scraper function to get a list of city codes and names by taking a URL as input. The function uses the requests library to get the HTML content from the URL and parse it using the BeautifulSoup library.

City URL Scraper: The script uses the get_city_url function to extract all the city URLs from the web page. The function starts by defining a core_url which will be used as the base for all the city URLs that will be extracted. It then defines a list of tables that contain strings representing table headers. The BeautifulSoup object is used to search for all 'td' elements that have the class "cislo" and a header specified in the tables list.

Voter Turnout Data: The script uses the voter_turnout_data function to extract data from the city URLs. The function uses the BeautifulSoup library and the requests library to extract data from the city URLs. The data is collected in the form of three lists: registered_voters, ballot_papers, and valid_votes.

Political Parties and Votes Scraper: The script uses the get_political_parties and get_votes functions to to extract names of political parties and number of votes from the city URLs.



Data Storage: The script uses the CSV library to store the data in a CSV file with the name specified by the user.


## Deployment

To run the script, you need to pass two command-line arguments: the URL and the file name. For example:

```bash
  python election_data.py "https://www.volby.cz/pls/ps2017nss/ps32?xjazyk=CZ&xkraj=12&xnumnuts=7101" file_name.csv

```
