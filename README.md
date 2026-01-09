# web_scraping_schools_in_Ghana
Ghana with a population of approximately 35.3 million people has schools all over the country. <br>
These schools are of different types and for different educational levels.

## Objective
This project aims to collect and structure comprehensive data on all active schools in Ghana using automated web scraping techniques. The data source for this project is the Ghana Education Directory, a trusted and authoritative platform that maintains up-to-date records of educational institutions across the country.

The website organizes schools by educational level and ownership type (public and private), with each category distributed across multiple paginated pages. To handle this structure, the project uses Python-based scraping logic built around reusable functions and controlled iteration to systematically extract data from every section.

The final output is a clean, structured dataset containing key information for each school, including institution name, type, education level, contact details, region, and location. This dataset is designed to support downstream analysis, visualization, geospatial mapping, and educational research applications. 

## Dataset/Website Information
the Ghana Education Directory: https://www.ghanaeducationdirectory.com/ 

In this website, the schools are divided into:
- the different educational levels
- Public/Private schools etc <br>
Each section contains a list of schools per section in blocks of 5, spanning a maximum number of pages depending on the number of schools.

Using 4 functions and 1 for loop I am able to extract each school's infromation:
- Name
- Type of Institution
- Institution level
- Contact (phone number)
- Region
- Location.

## Code Breakdown
The four functions are as follows:
1. **get_school_list_page()**: Constructs and sends HTTP requeststo the Ghana Education Directory Website using the query parameters school category, page number and sorting order.It validates the response and parses the HTML using **BeautifulSoup** 
2. **parse_school_list()**: Extracts structured data from a school listing page from HTML componenets, processes the metadata for each school and stores neatly in a dictionary per school.
3. **parse_school_detail()**: Scrapes detailed institutional information from individual school profile pages. Returning standardized, structured data.
4. **split_details()**: a cleaning function that splits the Phone number and location of a given school returning them as individual data pieces. <br>
Finally the **for loop** incorporates all the functions above to systematically extract, enrich, cleans, and aggregates educational institution data and stores the data in one variable. which is then converted into a dataframe and can be saved as a CSV.

### Next Steps
Automate this process to go through all the institutional data and section by section, page by page and store it all in one single file/variable. (Can be done in batches to reduce errors)
