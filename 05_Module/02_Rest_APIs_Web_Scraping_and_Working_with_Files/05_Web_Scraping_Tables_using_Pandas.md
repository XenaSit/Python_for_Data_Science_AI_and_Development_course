# Web Scraping Tables using Pandas

The Pandas library in Python contains a function <span style="color:orange;"> read_html() </span>  that can be used to extract tabular information from any web page.

Consider the following example:

Let us assume we want to extract the list of the largest banks in the world by market capitalization, from the following link:

    URL = 'https://en.wikipedia.org/wiki/List_of_largest_banks'

We may use <span style="color:orange;"> pandas.read_html() </span> function in python to extract all the tables in the web page directly.

A snapshot of the webpage is shown below.


We can see that the required table is the first one in the web page.

- Note: This is a live web page and it may get updated over time. The image shown above has been captured in November 2023. The process of data extraction remains the same.

We may execute the following lines of code to extract the required table from the web page.

            import pandas as pd
            URL = 'https://en.wikipedia.org/wiki/List_of_largest_banks'
            tables = pd.read_html(URL)
            df = tables[0]
            print(df)

This will extract the required table as a dataframe <span style="color:orange;"> df </span>. The output of the print statement would look as shown below.



Although convenient, this method comes with its own set of limitations.
Firstly, web pages may have content saved in them as tables but they may not appear as tables on the web page.

For instance, consider the following URL showing the list of countries by GDP (nominal).

    URL = 'https://en.wikipedia.org/wiki/List_of_countries_by_GDP_(nominal)'

The images on the web page are also saved in tabular format. A snapshot of the web page is shared below.


Secondly, the contents of the tables in the web pages may contain elements such as hyperlink text and other denoters, which are also scraped directly using the pandas method. This may lead to a requirement of further cleaning of data.
A closer look at table 3 in the image shown above indicates that there are many hyperlink texts which are also going to be treated as information by the pandas function.



We can extract the table using the code shown below.

    import pandas as pd
    URL = 'https://en.wikipedia.org/wiki/List_of_countries_by_GDP_(nominal)'
    tables = pd.read_html(URL)
    df = tables(2) # the required table will have index 2
    print(df)

The output of the print statement is shown below.



Note that the hyperlink texts have also been retained in the code output.

It is further prudent to point out, that this method exclusively operates only on tabular data extraction. BeautifulSoup library still remains the default method of extracting any kind of information from web pages.

# <a>Author(s)</a>
Abhishek Gagneja