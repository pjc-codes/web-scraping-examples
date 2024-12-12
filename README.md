# Web-Scraping (using Beautiful Soup)

There are three examples in this repo.

1. **Quotes.ipynb** : Scraping quotes from https://quotes.toscrape.com/
2. **Countries.ipynb** : Scraping country details from https://www.scrapethissite.com/pages/simple/
3. **Hockey.ipynb** : Scraping hockey team details from https://www.scrapethissite.com/pages/forms/

The data generated through the scraping is also provided as text files (.txt). The notebooks have code and steps explained therein. 

### **Steps for scraping in a nutshell:**

1. Import the necessary packages:
   - `import requests` 
   - `from bs4 import BeautifulSoup` 
2. Use `requests.get()` to retrieve the necessary details of the page to be scraped.
   
   - `page = requests.get("page_url")` where `page_url` is the URL of page to be scraped.
   - can check `page.status_code` to know if the connection is fine ie `status_code = 200` else `status_code = 404` for some error such as if the page doesnt exist.
3. Use `BeautifulSoup` to create a soup object as `page_soup = BeautifulSoup(markup = page.content, features= "html.parser")` or simply, `page_soup = BeautifulSoup(page.content, "html.parser")`. 
   
4. Alternatively, we can also use `page_soup = BeautifulSoup(page.text, "html.parser")`. `page.content` returns `binary` data whereas `page.text` returns `string` data.
   
   Now, this object holds the `html` codes for the page we are dealing with. 
   
5. Next step is to extract the relevant details via inspecting the code. This can be achieved with the `find`,`findAll`,`findChild` in conjunction with `get` and `getText` methods.
