# Using python to get data  from an existing URL reporting covid-19 data

[Building a COVID19 Vaccine Tracker Using Python](https://www.geeksforgeeks.org/build-a-covid19-vaccine-tracker-using-python/)


Create a Virtual Environment for the Project:

```
python3 -m venv env
```

Pip Install the Dependencies from the Requirements File

```
pip install -r requirements.txt
```

## Modules Needed

`bs4`: Beautiful Soup(bs4) is a Python library for pulling data out of HTML and XML files.


**Installation**
```
pip install bs4
```

`requests`:  Requests allows you to send HTTP/1.1 requests extremely easily.

**Installation**
```
pip install requests
```

**Approach:**

- Extract data form given URL
- Scrape the data with the help of requests and Beautiful Soup
- Convert that data into html code.
- Find the required details and filter them.

## Code Breakdown

[vaccinetracker.py](https://github.com/dennisnderitu254/Building-a-COVID19-Vaccine-Tracker-Using-Python/blob/main/vaccinetracker.py)

1. Importing Libraries:

`import requests`: This line imports the requests library, which is used for making HTTP requests to fetch data from websites.

`from bs4 import BeautifulSoup`: This imports the BeautifulSoup library, which is used for parsing HTML content and extracting specific data elements.

2. Defining a Function to Get Data:

`def getdata(url):`: This defines a function named getdata that takes a URL as input.
- `r = requests.get(url)`: This makes a GET request to the specified URL and stores the response in the variable `r`.
- `return r.text`: This returns the text content of the response, which contains the HTML of the webpage.

3. Fetching Data from the Website:

`htmldata = getdata("https://covid-19tracker.milkeninstitute.org/")`: This calls the `getdata` function to fetch the HTML content from the specified URL and stores it in the variable `htmldata`.

4. Parsing the HTML Content:

`soup = BeautifulSoup(htmldata, 'html.parser')`: This creates a BeautifulSoup object called `soup` by parsing the `htmldata` using the `html.parser`. This object is used for navigating and searching the HTML content.

5. Extracting Specific Data:

`result = str(soup.find_all("div", class_="is_h5-2 is_developer w-richtext"))`: This finds all `div` elements with the specified class attributes and converts the `result` to a string, storing it in the variable result. These elements likely contain the content the code is targeting.

6. Printing Selected Extracted Data:

The code then prints specific slices of the `result` string, which likely represent different pieces of information extracted from the targeted elements. The specific meaning of these slices would depend on the structure of the HTML content on the website.

