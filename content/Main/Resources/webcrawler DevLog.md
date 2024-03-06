[[webcrawler DevLog]]

[How to Build a Web Scraper With Python [Step-by-Step Guide] | HackerNoon](https://hackernoon.com/how-to-build-a-web-scraper-with-python-step-by-step-guide-jxkp3yum)

[[Inklutech]]

[JaYani55/Jobs-Webcrawler-Inklu (github.com)](https://github.com/JaYani55/Jobs-Webcrawler-Inklu)
# Webscraper

Neues Paradigma: Labor Market OSINT Tool
- Deep analysis of company job postings, spezifische companies (Input data, company name, Career Page URL)
- Weiterentwicklung zu den basic requirements für Inklupreneur (Aber erstmal das fertig machen)
- Tbh, kein GUI notwendig, würde zu viel Zeit kosten. Terminal reicht.


# DevLog

## Roadmap

- [x] Scraper, Base (Static) ✅ 2024-01-08
- [x] [[GPT]] Datafizierungsagent ✅ 2024-01-08
- [x] Scraper, non-static (Selenium)
- [x] Seatable Integration
- [x] Erste Version komplett
- [x] ST Datenübertragung von Big Data Base auf Stellenprofile
- [x] Code-Agent für Replikation
	- [x] Aufgeteilt in: Static / Dynamic
- [x] Ausschreibung ganztext übertragen
- [x] Einzelcrawler zusammenführen
- [x] Dataframe speichern Zwischenschritt
- [x] Seatable Übertragung abgetrennt
- [ ] Replizieren für alle Unternehmen
- [x] Abgleichfunktion (GET ST, vergleich mit Crawl nach gelöschten Einträgen, markieren)
- [ ] GPT Datafizierungsagent ersetzen mit OpenAI-API (Mistral AI?)
- [ ] GUI
- [ ] Optionen, bestimmte Crawls auswählen, Abgleich auswählen
- [ ] Einbindung, Inklupreneur
- [ ] Start [[OSINT]] Labor Analysis ([[LOSINT]])
- [ ] Github Project, fork of Inklu Version
- [ ] Scraper Funktionalitäten
- [ ] Datafizierungsfunktionalitäten

## Development

### Environment

1. Installiere das Crawler Verzeichnis

``` Powershell
git pull https://github.com/JaYani55/Jobs-Webcrawler-Inklu
```


2. Virtual Environment (Im Directory selbst. env muss im directory erstellt werden ansonsten hat etwas nicht geklappt)

``` powershell
python -m venv env
```
(Terminal muss in 'env' modus sein)

Env aktivieren:
``` Powershell
env\Scripts\Activate.ps1
```

ExecutionPolicy muss freigegeben sein. 
Check:
``` Powershell
Get-ExecutionPolicy
```

Wenn nicht:
Powershell als Admin öffnen
``` Powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
```

3. Install packages

``` powershell
pip install selenium
pip install beautifulsoup4
pip install bs4
pip install datetime
pip install pandas
pip install requests
```

4. Install webdriver

Geh zu:
[Chrome for Testing availability (googlechromelabs.github.io)](https://googlechromelabs.github.io/chrome-for-testing/)
Lade chrome (win64) herunter und chromedriver (win64). Entpacke im directory
(Development version 120.0.6099.109)

## Modellierung

![[Pasted image 20240306143941.png]]
- Implemented, see Version 0.3.0

# Versionierung

## Scraper Code V 1.0

### Documentation Tutorial

```
To create a webcrawler in Python, you can use libraries like Beautiful Soup and requests. Here are the general steps:

1. Install the required libraries:

Shell Script

Copy

Insert

`   pip install beautifulsoup4 requests   `

2. Write a script to send an HTTP request using the requests library to fetch the HTML content of the webpage.
    
3. Use Beautiful Soup to parse the HTML content and extract the relevant data, such as links, text, or other information.
    
4. Iterate through the links and repeat the process to crawl through multiple web pages.
    

Please note that web crawling should be done responsibly and in accordance with the website's terms of service.
```

### Code

#### HTTP Request

```
import requests

url = 'https://inklupreneur.de/stellenprofile/'
response = requests.get(url)
print(response.text)
```

#### Python Parser

##### Explanation
- In that case, you would need to use a tool like Selenium to run JavaScript in a browser context and extract the data from the webpage. BeautifulSoup alone cannot execute JavaScript code as it is used for parsing static HTML and XML files. If you're working with client-side JavaScript, using Selenium along with a web driver would be a more appropriate approach.

```



# Libraries

import requests
from bs4 import BeautifulSoup

# HTTP Request
url = 'https://inklupreneur.de/stellenprofile/'
response = requests.get(url)
print(response.text)

# Parser
html_content = response.text
soup = BeautifulSoup(html_content, 'html.parser')
headline = soup.select_one("#page-header > div > div.entry-header-text.page-header-text > h1")
print(headline.text)

job_listings_ul = soup.select_one("#main > article > div.entry-content.entry-content-singular > div.job_listings > ul")
print(job_listings_ul)

new_selector = soup.select_one("#wrapper-matching-20570 > a > div.position > h3")
print(new_selector)
```

#### Selenium Parser

```
The provided code does not contain any references to Selenium or web drivers. However, I can explain them to you.

Selenium is a tool that allows you to automate interactions with web browsers. It allows you to write scripts to simulate interactions such as clicking on buttons, filling out forms, and navigating through web pages.

A web driver is a program that facilitates communication between your code and a specific web browser. It acts as an intermediary, translating your commands into actions within the browser and gathering information from the browser to return to your code. This enables you to automate tasks and extract information from web pages programmatically.
```

```
from selenium import webdriver

options = webdriver.ChromeOptions()
options.add_argument("--no-sandbox")  # Bypass OS security model
options.add_argument("--disable-dev-shm-usage")  # Overcome limited resource problems

driver =
webdriver.Chrome('/nix/store/n4qcnqy0isnvxcpcgv6i2z9ql9wsxksw-chromedriver-114.0.5735.90/bin/chromedriver', options=options)
url = 'https://inklupreneur.de/stellenprofile/'
driver.get(url)

element = driver.find_element_by_css_selector("#wrapper-matching-20571 > a > div.position")
print(element.text)

driver.quit()

```

### Jobportale Code
### Inklupreneur Jobportal

#### class Joblist

```
#main > article > div.entry-content.entry-content-singular > div.job_listings > ul
```

#### Class Position
(Javscript)
```
document.querySelector("#wrapper-matching-20571 > a > div.position")

```

#### class Position

```
#wrapper-matching-20570 > a > div.position

```

apt-get install chromium-chromedriver

pip install chromedriver-py


apt-get install chromium-chromedriver
E: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), are you root?
Detected change in environment, reloading shell...



## Scraper Code V 1.1

``` Python
from selenium import webdriver

# Initialize the Chrome WebDriver
driver = webdriver.Chrome("C:\\Users\\Janal\\Downloads\\chromedriver_win32\\chromedriver.exe")

# Open the webpage
driver.get("(redacted)")

try:
    # Locate the element using XPath and extract the text
    element = driver.find_element_by_xpath('//*[@id="6"]/div[4]/div/div[1]/div/table/tbody/tr[1]/td[1]/a')
    extracted_text = element.text
    print(extracted_text)

    # If you want to extract the href attribute (link), use get_attribute
    extracted_link = element.get_attribute('href')
    print(extracted_link)

finally:
    # Close the WebDriver
    driver.quit()

```

- Current issue: Environment issue, selenium not installing. Brush up on that, get into the basic concepts [[development environment]]

## Scraper Code V 1.2 --selenium is supremely annoying (XPath change, Webdriver PATH Change)

```Python
from selenium import webdriver

driver = webdriver.Chrome()
# Initialize the Chrome WebDriver
# driver = webdriver.Chrome(executable_path="C:\\Users\\Janal\\Downloads\\chromedriver_win32\\chromedriver.exe")
# Open the webpage
driver.get("(redacted)")

try:
    berlin_element = driver.execute_script("return document.querySelector('body > div:nth-child(1) > div.sc-73r8cv-1.ilRiFP > main > div:nth-child(1) > section > div.sc-18h7are-0.ebVyJP > div.sc-1tu9fip-2.gJVWbp > div > div > div > div:nth-child(2) > div > div > div > div.sc-4j8eof-1.jFfmvQ > form > label.sc-11asbat-1.jMsFzw')")
    berlin_element.click()
    # Locate the element using XPath and extract the text
    element = driver.find_element("xpath", '//*[@id="6"]')                                 
    extracted_text = element.text
    print(extracted_text)

    # If you want to extract the href attribute (link), use get_attribute
    extracted_link = element.get_attribute('href')
    print(extracted_link)

finally:
    # Close the WebDriver
    driver.quit()

# ToDO: Add Link to the job offer, Extract URL and transform output for the table


```

- Fixed the issue
	- **Launch in a virtual environment**
	- Chrome (test) in the environment (120)
	- chromedriver in the environment (120)
	- added all three to .gitignore
- Selenium is supremely annoying. Two changes to the code, which GPT-4 doesn't know about.
	- [python 3.x - AttributeError: 'WebDriver' object has no attribute 'find_element_by_xpath' - Stack Overflow](https://stackoverflow.com/questions/72754651/attributeerror-webdriver-object-has-no-attribute-find-element-by-xpath)
	- find.element is structured differently now
		- Why the FUCK would you change that???
	- [TypeError: WebDriver.__init__() got an unexpected keyword argument 'executable_path' in Selenium Python - Stack Overflow](https://stackoverflow.com/questions/76550506/typeerror-webdriver-init-got-an-unexpected-keyword-argument-executable-p)
	- Webdriver path calling changed

## Scraper Code V 0.1.3 -- Working version 




``` Python
from selenium import webdriver
from bs4 import BeautifulSoup
import pandas as pd
from datetime import datetime
import requests

# Initialize the Chrome WebDriver
driver = webdriver.Chrome()
crawl_date = datetime.now().strftime('%d_%m_%Y')
# Company specific variables
employer = '("redacted")'
driver.get("redacted")


# Click on the "Berlin" button to specify the location in the search form
berlin_element = driver.execute_script("return document.querySelector('body > div:nth-child(1) > div.sc-73r8cv-1.ilRiFP > main > div:nth-child(1) > section > div.sc-18h7are-0.ebVyJP > div.sc-1tu9fip-2.gJVWbp > div > div > div > div:nth-child(2) > div > div > div > div.sc-4j8eof-1.jFfmvQ > form > label.sc-11asbat-1.jMsFzw')")
berlin_element.click()
# Locate the element using XPath and extract the HTML
element = driver.find_element("xpath", '//*[@id="6"]')
extracted_html = element.get_attribute('outerHTML')
# Initialize the BeautifulSoup library and specify the parser
soup = BeautifulSoup(extracted_html, "html.parser")
# for test purposes use below to see the raw html structure
    #print(soup.prettify())

# Initialize Pandas, structure HTML into a list, and convert the list into a Pandas DataFrame
data = []
rows = soup.find_all('tr')
base_url = '(redacted)'
for row in rows:
    cols = row.find_all('td')
    if len(cols) < 3:
            continue
    job_title = cols[0].find('a').text if cols[0].find('a') else None
    department = cols[1].text if cols[1] else None
    location = cols[2].text if cols[2] else None
    relative_url = cols[0].find('a')['href'] if cols[0].find('a') else None
    url = base_url + relative_url

    data.append([job_title, department, location, url, employer, crawl_date])

df = pd.DataFrame(data, columns=['Job Title', 'Department', 'Location', 'URL', 'employer', 'crawl_date'])
# for test purposes use below to see the dataframe output
    #print(df)

# Seatable API POST Call
import requests
url = "https://cloud.seatable.io/dtable-server/api/v1/dtables/f08313ab-c626-4cad-aad7-6db677b7749f/rows/"
headers = {
    "accept": "application/json",
    "content-type": "application/json",
    # remove bearer token for security reasons
    "authorization": "Bearer (redacted)
}
# Iterate over the rows in the DataFrame
for _, row in df.iterrows():
    # Create the payload for the API request
    payload = {
        "row": {
            "Job Title": row['Job Title'],
            "Department": row['Department'],
            "URL": row['URL'],
            "Location": row['Location'],
            "employer": row['employer'],
            "crawl_date": row['crawl_date']
        },
        "table_name": "Inklupreneur Recruiting_Stellenprofile_BD"
    }

    # Make the POST request to the API
    response = requests.post(url, json=payload, headers=headers)
    print(response.text)



    #extracted_text = element.text
    #print(extracted_text)

    # Parse the extracted HTML using BeautifulSoup
    #job_title_element =  soup.select_one("#\36  > div:nth-child(2) > div > div.sc-1dywz0m-0.exQcZ > div > table > tbody > tr:nth-child(1) > td:nth-child(1) > a")
    #job_title = job_title_element.text if job_title_element else None
    #print('Job Title:', job_title)


# Close the WebDriver
driver.quit()

# ToDO: At the end, add a function that will compare the seatable data with another crawl to detect which jobs have been deleted and mark them as deleted in seatable
```

## Scraper Code V0.3.0

- See model up above
- This code is a unified run function that calls each crawler
	- Crawlers scrape the data and save it as a dataframe 
- The dataframes are pulled and concetenated
- Compare the entries of the dataframe with entries in the database to see which entries have been removed from the websites and which are new to the database.
	- Flag removed to database to remove from job portal
	- Add new entries to the database
- Then, a seperate description crawler is called to open the links of all the new entries to pull the job description.
- Also, added a configuration file to skip certain functionalities or modules for testing purposes.

```Python
import os
import requests
import time
import datetime
import numpy as np
import pandas as pd
import importlib
import logging
import sys
import subprocess
import configparser

# Set environment variables for crawlers and SeaTable API URL and token
os.environ['CRAWLERS'] = 'Allos_Hof_Manufaktur,Autismus_Bremen,KFZTeile24,MBition,UNIQLO,NORDSEE,MyEnso,TanteEnso,encoway,Scout24'
os.environ['SEATABLE_API_URL'] = 'https://cloud.seatable.io/dtable-server/'
# Get API access token from BTG_ST.py script
api_token_process = subprocess.run(['python', 'Tools/BTG_ST.py'], stdout=subprocess.PIPE)
api_token = api_token_process.stdout.strip().decode()
os.environ['SEATABLE_API_TOKEN'] = api_token

# Load configuration from config file
config = configparser.ConfigParser()
config.read('config.ini')
print(config.sections())
#with open('config.ini', 'r') as f:
   # print(f.read())
SKIP_CRAWLERS = config.getboolean('crawlers', 'skip_crawlers')

# Set up logging
logger = logging.getLogger(__name__)
logger.setLevel(logging.INFO)
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(funcName)s - %(message)s')
console_handler = logging.StreamHandler()
console_handler.setFormatter(formatter)
logger.addHandler(console_handler)

# Load configuration from environment variables and config file
SEATABLE_API_URL = os.environ.get('SEATABLE_API_URL')
if not SEATABLE_API_URL:
    SEATABLE_API_URL = config.get('seatable', 'api_url')
SEATABLE_API_TOKEN = os.environ.get('SEATABLE_API_TOKEN')
if not SEATABLE_API_TOKEN:
    SEATABLE_API_TOKEN = config.get('seatable', 'api_token')
CRAWLERS = os.environ.get('CRAWLERS').split(',')
if not CRAWLERS:
    CRAWLERS = config.get('crawlers', 'crawler_list').split(',')
SKIP_CRAWLERS = config.getboolean('crawlers', 'skip_crawlers')

# Function to check access token
def check_access_token():
    url = SEATABLE_API_URL + 'dtables/0e931781-c2f5-4f72-836f-adb0f15d7234'
    print(url)
    headers = {'accept': 'application/json', 'authorization': f'Bearer {SEATABLE_API_TOKEN}'}
    print(headers)
    try:
        response = requests.get(url, headers=headers)
        if response.status_code == 401:
            logger.error('Access token expired')
            sys.exit(1)
        elif response.status_code >= 400:
            logger.error(f'An error occurred: HTTP Status Code {response.status_code}')
            sys.exit(1)
        else:
            logger.info('Authentication Token is Valid')
    except Exception as e:
        logger.error(f'An error occurred: {e}')
        sys.exit(1)

# Function to generate unique ID
def generate_unique_id():
    cache_file_path = 'Data/Crawlers/DFCache/last_id.txt'
    if not os.path.exists(cache_file_path):
        with open(cache_file_path, 'w') as file:
            file.write('1')
        return 1
    with open(cache_file_path, 'r') as file:
        last_id = int(file.read().strip())
    new_id = last_id + 1
    with open(cache_file_path, 'w') as file:
        file.write(str(new_id))
    return new_id

# Function to run crawlers
def run_crawlers():
    for crawler_name in CRAWLERS:
        try:
            crawler_module = importlib.import_module(f'Data.Crawlers.{crawler_name}')
            crawler_module.run()
        except Exception as e:
            logger.error(f'An error occurred while running crawler {crawler_name}: {e}')


# Function to concatenate dataframes
def concatenate_dataframes():
    directory = 'Data/Crawlers/DFCache/CrawlerOutput'
    dataframes = []
    for filename in os.listdir(directory):
        if filename.endswith('.csv'):
            filepath = os.path.join(directory, filename)
            df = pd.read_csv(filepath)
            dataframes.append(df)
    concatenated_df = pd.concat(dataframes, ignore_index=True)
    concatenated_df['crawl_id'] = concatenated_df.apply(lambda _: generate_unique_id(), axis=1)
    concatenated_df.to_csv('Data/Crawlers/DFCache/concatenated.csv', index=False)
    logger.info('Dataframe successfully concatenated and saved to Data/Crawlers/DFCache/concatenated.csv')

# Function to fetch data from SeaTable API
def fetch_seatable_data():
    url = SEATABLE_API_URL + 'api/v1/dtables/0e931781-c2f5-4f72-836f-adb0f15d7234/rows/?table_name=IPR_BigData_Inklupreneur_Recruiting_Stellenprofile_BD&view_name=Crawler_Compare'
    headers = {'accept': 'application/json', 'authorization': f'Bearer {SEATABLE_API_TOKEN}'}
    try:
        response = requests.get(url, headers=headers)
        response.raise_for_status()
        #return pd.json_normalize(response.json()['rows'])
        df = pd.json_normalize(response.json()['rows']).query("removed != True")
        df.to_csv('Data/Crawlers/DFCache/DF_DB.csv', index=False)
        #logger.info('DF_DB successfully saved to Data/Crawlers/DFCache/DF_DB.csv')
        return df
    except requests.exceptions.RequestException as e:
        logger.error(f'An error occurred: {e}')
        sys.exit(1)

# Function to load latest data
def load_latest_data():
    return pd.read_csv('Data/Crawlers/DFCache/concatenated.csv')

# Function to compare and update data
def compare_and_update(dfDB, dfLatest):
    dfDB = pd.read_csv('Data/Crawlers/DFCache/DF_DB.csv')
    dfLatest = pd.read_csv('Data/Crawlers/DFCache/concatenated.csv')
    
    # First filter dfDB
    #dfDB = dfDB[dfDB['removed'] != 'true']
    #print(dfDB)
    
    # Now determine removed_job_ids
    removed_job_ids = dfDB[(~dfDB['job_title'].isin(dfLatest['job_title'])) & (dfDB['removed'] != 'True')]['_id'].tolist()
    print(f'removed: {removed_job_ids}')
    dfNewJobs = dfLatest[~dfLatest['job_title'].isin(dfDB['job_title'])]
    if removed_job_ids:
        update_seatable(removed_job_ids)
    dfNewJobs.to_csv('Data/Crawlers/DFCache/DF_Final.csv', index=False)
    logger.info('Final DataFrame successfully saved.')

# Function to update SeaTable API
def update_seatable(removed_job_ids):
    url = SEATABLE_API_URL + 'api/v1/dtables/0e931781-c2f5-4f72-836f-adb0f15d7234/batch-update-rows/'
    #url = "https://cloud.seatable.io/dtable-server/api/v1/dtables/0e931781-c2f5-4f72-836f-adb0f15d7234/batch-update-rows/"
    updates = [{'row': {'removed': 'true'}, 'row_id': row_id} for row_id in removed_job_ids]
    payload = {'table_name': 'IPR_BigData_Inklupreneur_Recruiting_Stellenprofile_BD', 'updates': updates}
    headers = {'accept': 'application/json', 'content-type': 'application/json', 'authorization': f'Bearer {SEATABLE_API_TOKEN}'}
    try:
        response = requests.put(url, json=payload, headers=headers)
        response.raise_for_status()
        logger.info(response.text)
    except requests.exceptions.RequestException as e:
        logger.error(f'An error occurred: {e}')
        sys.exit(1)

# Function to upload data to SeaTable API
def upload_data():
    df = pd.read_csv('Data/Crawlers/DFCache/DF_Final.csv')
    df.replace([pd.NA, pd.NaT, np.inf, -np.inf], 'None', inplace=True)
    df = df.replace({np.nan: None})
    url = SEATABLE_API_URL + 'api/v1/dtables/0e931781-c2f5-4f72-836f-adb0f15d7234/batch-append-rows/'
    payload = {'table_name': 'IPR_BigData_Inklupreneur_Recruiting_Stellenprofile_BD', 'rows': df.to_dict('records')}
    #print(payload)
    headers = {'accept': 'application/json', 'content-type': 'application/json', 'authorization': f'Bearer {SEATABLE_API_TOKEN}'}
    try:
        response = requests.post(url, json=payload, headers=headers)
        response.raise_for_status()
        logger.info(response.text)
    except requests.exceptions.RequestException as e:
        logger.error(f'An error occurred: {e}')
        sys.exit(1)

# Function to run description crawlers
def run_desc_crawlers():
    logger.info('Running description crawlers')
    dfDB = fetch_seatable_data()
    excluded_employers = ["TanteEnso", "Scout24", "encoway"]
    #config = configparser.ConfigParser()
    #config.read('config.ini')
    #excluded_crawlers = config['DescCrawlers']['exclude'].split(',')
    #logger.info(f'Excluded crawlers: {excluded_crawlers}')

    # Filter rows that need description crawled
    df_to_crawl = dfDB.loc[dfDB['Desc'] != True]

    # Exclude employers specified in config
    df_to_crawl = df_to_crawl[~df_to_crawl['employer'].isin(excluded_employers)]

    # Prepare DescURL.csv
    desc_url_df = df_to_crawl[['job_title', 'URL', 'employer', 'crawl_id', '_id']]
    desc_url_df['processed'] = False
    desc_url_df.to_csv('Data/DescCrawler/DescURL.csv', index=False)
    if desc_url_df.empty:
        print("No valid entries found in DescURL.csv. Skipping crawling process.")
        return  # Exit the function early
    print(desc_url_df)
    processed_crawl_ids = set()
    desc_output_path = 'Data/DescCrawler/DescOutput'

    for _, row in desc_url_df.iterrows():
        employer, crawl_id = row['employer'], row['crawl_id']
        # Format the expected markdown filename based on employer and crawl_id
        md_filename = f"{employer}_{crawl_id}.md"
        full_md_path = os.path.join(desc_output_path, md_filename)

        # Check if this crawl_id has been processed or if the markdown file already exists
        if crawl_id in processed_crawl_ids or os.path.exists(full_md_path):
            print(f"Skipping crawler for {employer} with crawl_id {crawl_id}: already processed or file exists.")
            continue  # Skip to the next entry if already processed or file exists

        # The module name path corrected to match Python's import syntax
        module_name = f"Data.DescCrawler.{employer.replace(' ', '_')}_Desc"
        try:
            desc_crawler_module = importlib.import_module(module_name)
            # Check if the imported module has a 'run' method
            if hasattr(desc_crawler_module, 'run'):
                try:
                    # Call the 'run' method from the module
                    desc_crawler_module.run()
                    print(f"Successfully executed crawler for {employer}")
                except Exception as e:
                    # Log any errors that occur during the crawler execution and include the crawl_id
                    print(f"Error executing crawler for {employer}, crawl_id {crawl_id}: {e}")
                    continue  # Skip to the next entry
            else:
                print(f"No 'run' method found for {employer} crawler.")
        except ModuleNotFoundError:
            logger.error(f"Module not found for {employer}, skipping...")
            continue

    # Add the crawl_id to the set of processed IDs to avoid reprocessing
    processed_crawl_ids.add(crawl_id)

def update_descriptions():
    desc_url_df = pd.read_csv('Data/DescCrawler/DescURL.csv')
    for _, row in desc_url_df.iterrows():
        employer, crawl_id, _id = row['employer'], row['crawl_id'], row['_id']
        md_filename = f"Data/DescCrawler/DescOutput/{employer}_{crawl_id}.md"
        try:
            with open(md_filename, 'r', encoding='utf-8') as md_file:
                description_content = md_file.read()
                url = SEATABLE_API_URL + 'api/v1/dtables/0e931781-c2f5-4f72-836f-adb0f15d7234/batch-update-rows/'
                payload = {'table_name': 'IPR_BigData_Inklupreneur_Recruiting_Stellenprofile_BD', 'updates': [{'row': {'description': description_content, 'Desc': 'true'}, 'row_id': _id}]}
                headers = {"accept": "application/json", "content-type": "application/json", 'Authorization': f'Bearer {SEATABLE_API_TOKEN}'}
                response = requests.put(url, json=payload, headers=headers)
                response.raise_for_status()
                logger.info(f"Updated description for _id: {_id}")
        except Exception as e:
            logger.error(f"An error occurred while updating description for _id: {_id} - {e}")

if __name__ == '__main__':
    while True:
        check_access_token()
        if not SKIP_CRAWLERS:
            run_crawlers()
        else:
            logger.info('Skipping run_crawlers() as per config file.')
            dfLatest = load_latest_data()
        concatenate_dataframes()
        dfDB = fetch_seatable_data()
        dfLatest = load_latest_data()
        compare_and_update(dfDB, dfLatest)
        upload_data()
        run_desc_crawlers()
        update_descriptions()
        logger.info('Loop ended')
        time.sleep(3600)

```



# Tools
## Scrapy
- Python Framework
- https://scrapy.org/
- https://www.youtube.com/watch?v=mBoX_JCKZTE
	- Tutorial video, Course 

## Selenium
- Web Browser Automation Framework
- For conducting in-browser navigation actions 
	- Clicking through links, forms, navigation structures etc.
- https://www.selenium.dev/
- Selenium IDE
	- Tool for recording automation tasks and identifying navigation structures
	- https://www.selenium.dev/selenium-ide/
