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
	- [ ] Aufgeteilt in: Static / Dynamic
- [ ] Ausschreibung ganztext übertragen
- [ ] Einzelcrawler zusammenführen
- [ ] Dataframe speichern Zwischenschritt
- [ ] Seatable Übertragung abgetrennt
- [ ] Replizieren für alle Unternehmen
- [ ] Abgleichfunktion (GET ST, vergleich mit Crawl nach gelöschten Einträgen, markieren)
- [ ] GPT Datafizierungsagent ersetzen mit OpenAI-API
- [ ] GUI
- [ ] Optionen, bestimmte Crawls auswählen, Abgleich auswählen
- [ ] Einbindung, Inklupreneur
- [ ] Zusammenführen mit GPT
- [ ] Start [[OSINT]] Labor Analysis ([[LOSINT]])
- [ ] Github Project, fork of Inklu Version
- [ ] Scraper Funktionalitäten
- [ ] Datafizierungsfunktionalitäten
- [ ] LinkedIn Intelligence Einbindung

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
driver.get("https://jobs.kfzteile24.de/jobs")

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
driver.get("https://jobs.kfzteile24.de/jobs")

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

## Scraper Code V 1.3 -- Working version 


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
employer = 'KFZTeile24'
driver.get("https://jobs.kfzteile24.de/jobs")


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
base_url = 'https://jobs.kfzteile24.de'
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
    "authorization": "Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJleHAiOjE3MDU1ODkwMjMsImR0YWJsZV91dWlkIjoiZjA4MzEzYWItYzYyNi00Y2FkLWFhZDctNmRiNjc3Yjc3NDlmIiwidXNlcm5hbWUiOiIiLCJwZXJtaXNzaW9uIjoicnciLCJhcHBfbmFtZSI6IkNyYXdsZXIifQ.m1iW7U97kp_uPwQ5gJa9cFEiJmlc6fTiXLR9P81nV9E"
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

# Tools
## Scrapy
- Python Framework
- https://scrapy.org/
- https://www.youtube.com/watch?v=mBoX_JCKZTE
	- Tutorial video, Course 

## Octoparse
- SaaS solution
	- Too expensive, but maybe free plan will be enough for a start
	- https://www.octoparse.com/pricing
