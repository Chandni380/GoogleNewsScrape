# GoogleNewsScrape
Google news scrapper using Python and Beautiful Soup

•	The first task is to install GoogleNews and newspaper3k for parsing the article which can be accomplished with the following statement.
!pip install GoogleNews
!pip install newspaper3k
 
Also install beautiful Soup. It is a library that allows you to efficiently and easily pull out information from HTML
pip install beautifulsoup4
 
•	After importing libraries please click enter and add below mentioned code.
from GoogleNews import GoogleNews
from urllib.request import Request, urlopen
from bs4 import BeautifulSoup
import requests
import html5lib
import pandas as pd

googlenews = GoogleNews()
googlenews = GoogleNews(lang = 'en', region = "CA", period = "1y")
googlenews.set_encode('utf-8')
googlenews.search('sensory friendly Canada')

#googlenews.set_encode('utf-8')

for i in range (2, 5):
    googlenews.getpage(i)
    records = googlenews.result()
#title = googlenews.gettext()
    df = pd.DataFrame(records, columns = ['title', 'link','datetime'])
df.head()
df.to_csv('canadaNewsData.csv', date_format='%Y-%m-%d')

•	Code criteria and keywords can be modified as per requirement. Currently this code is particulary for Canada data.
•	After adding code click on the Run button on top ribbon of notebook.

•	After the code run without any error go back to the home page of the of Jupyter notebook where a csv file can be found. Check mark the file and click on download option that appears on top ribbon of home page. 
•	Once you click download you can see file downloaded on bottom left corner.
