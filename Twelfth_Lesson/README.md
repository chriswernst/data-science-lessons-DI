# Putting it all together - Your first program
##### December 5, 2017
###### by Chris Ernst
###

### Modules we may use(not exhaustive):
1. numpy (to analyze numbers / handle data)
2. os (to set directories)
3. matplotlib (to graph/plot)
4. Pandas (to export as csv/analyze data)
5. csv (to export as csv)
6. smptplib (for sending emails)
7. bs4 (for sorting through html)
8. requests (for pulling html pages)
9. lxml (for parsing html)

##### Where we left off:
```
import requests
import bs4
from lxml import html
from bs4 import BeautifulSoup
import webbrowser as wb

# Import all the libraries

page = requests.get('https://losangeles.craigslist.org/search/sss?query=prius&sort=rel')
# Set the page to the target URL

tree = html.fromstring(page.content)
# Build html tree

soup = BeautifulSoup(page.text, 'html.parser')
# Parse with bs4

URL = ('https://losangeles.craigslist.org/search/sss?query=prius&s=' + str(num) + '&sort=rel' )

num = 120
# This is page one
# Loop through pages
for i in range(5):
    num = num+120
    URL = ('https://losangeles.craigslist.org/search/sss?query=prius&s=' + str(num) + '&sort=rel' )
    
    page = requests.get(URL)
    # Set the page to the target URL
    
    tree = html.fromstring(page.content)
    # Build html tree
    
    soup = BeautifulSoup(page.text, 'html.parser')
    # Parse with bs4
```
