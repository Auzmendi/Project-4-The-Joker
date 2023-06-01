# Project-4-The-Joker
This is ithe project 4 of the bootcamp for data analytics of Iron Hack
The target of the project is to webscrape data from 2 different webpages in order to find find some profitable business oportunities. In this case they will be Aliexpress & Amazon. The idea is gather an extensive dataset with information about products (we will focus on videogames related products).
Once the dataset are cleaned, we will try to find matches in the products from both webpages. Then we will study the differences in price, delivery time and so on. Returning information about the most profitable oportunities.
With all this information we will create 2 different bussineses.
    - Start our own company of drop shipping attending to the result obteined.
    - Start our own company of data selling, in order to help other small companies which will need information actualized and clenaned about the products of this companies. 

The code is divided in several parts.


ALIEXPRESS WEBSCRAPER

    The code in Python, use 2 diferent modules to be able to wenbscrap the Aliexpress webpage. Using selenium, the program does the required steps to get the first page that will be scraped(inccluding down scrolling). Once there, using the module BeautifulSoup, it gets the html. Taking advantage of a for loop, the program will webscrape data from the first 100 pages of that kind of products. This will be done using patterns to modiify the url when we want to move from one webpage to the next one. 

    In each loop the data will be collected in a partial df which will be concatenated to the main one, called global_dataframe. 

    Once the lobal_dataframe is finished it will saved as a not_cleaned_csv file first.
    The df will pass trhoughout several steps of dataclenaning and then another csv will be created. In this case, yes, the finished one.

    To code this program we have used different functions:

        - time_randomizer(t1,t2): this function applies a time.sleep method during x second. And x second are chosen randomly between 2 numbers t1 & t2.
                            t1 minimum time & t2 maximum time. 

        - starting_setup(): this function uses module selenium to follow several steps. 
            1) Open a new window with the browser Chrome.
            2) Goes to aliexpress webpage
            3) Click on accept cookies
            4) Click on category "electronics"
            5) Click on category "videogames"
            6) Click on "sort by order quantity"
            7) Click on "sort by rating>=4"
            8) Scroll down to the botton of the webpage
        
        - page_scraper(html):  this function uses module BeautifulSoup to scrap data from the current webpage. Its input is the html which has been       collected in the main program. It gets the data and turn them into lists and after that turn the lists into df, which is the return of the function.

        -It is planned to code some other usefull functions to work on the global_dataframe 
            1) filters
            2) sorters
            3) ploters
        

AMAZON WEBSCRAPER



