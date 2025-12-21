# web_scraping_schools_in_Ghana
Ghana with a population of approximately 35.3 million people has schools all over the country. <br>
These schools are of different types and for different educational levels.

## Objective
To collect information on all schools present in Ghana I referred to the **Ghana Education Directory** which has the most accurate data on all active schools in Ghana. 

## Dataset/Website Information
the Ghana Education Directory: https://www.ghanaeducationdirectory.com/ 

In this website, the schools are divided into:
- the different educational levels
- Public/Private schools etc <br>
Each section contains a list of schools per section in blocks of 5, spanning a maximum number of pages depending on the number oof schools

Using 3 functions and 1 for loop I am able to extract each school's infromation:
- Name
- Type of Institution
- Institution level
- Contact (phone number)
- Region
- Location.

## Code Breakdown
The three functions are as follows:
1. **get_school_list_page()**: Constructs and sends HTTP requeststo the Ghana Education Directory Website using the query parameters school category, page number and sorting order.It validates the response and parses the HTML using **BeautifulSoup** 
2. **parse_school_list()**: Extracts structured data from a school listing page from HTML componenets, processes the metadata for each school and stores neatly in a dictionary per school.
3. **parse_school_detail()**: Scrapes detailed institutional information from individual school profile pages. Returning standardized, structured data.
4. **split_details()**: a cleaning function that splits the Phone number and location of a given school returning them as individual data pieces. <br>
Finally the **for loop** incorporates all the functions above to systematically extract, enrich, cleans, and aggregates educational institution data and stores the data in one variable. which is then converted into a dataframe and can be saved as a CSV.

### Next Steps
Automate this process to go through all the institutional data and section by section, page by page and store it all in one single file/variable. (Can be done in batches to reduce errors)