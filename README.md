# Amazon_Web_Scraping

### Objective:
The code scrapes information about watches for men from multiple pages on Amazon, extracts relevant details like product title, price, rating, and reviews, and then performs some exploratory data analysis (EDA) and visualization on the collected data. Finally, it identifies the best watches under different price ranges.

### Code Explanation:

1. **Importing Libraries:**
    - `requests`: For making HTTP requests to fetch web pages.
    - `pandas`: For data manipulation and analysis.
    - `matplotlib` and `seaborn`: For data visualization.
    - `BeautifulSoup`: For web scraping HTML content.
    - `numpy`: For numerical operations.

2. **Functions:**
    - `prod_desc(new_soup)`: Extracts the product title from the BeautifulSoup object.
    - `review(new_soup)`: Extracts the number of reviews from the BeautifulSoup object.
    - `rating(new_soup)`: Extracts the product rating from the BeautifulSoup object.
    - `price(new_soup)`: Extracts the product price from the BeautifulSoup object.

3. **Data Collection Loop:**
    - The script iterates through pages (1 to 7) of Amazon search results for "watches for men."
    - For each page, it extracts links to individual product pages.

4. **Scraping Individual Product Pages:**
    - It visits each product page and extracts product details using the defined functions (`prod_desc`, `review`, `rating`, `price`).
    - The extracted information is then added to a dictionary `d`.

5. **Creating DataFrame:**
    - A pandas DataFrame `watches` is created from the collected data.
    - Rows with missing values in the "Title" and "Rating" columns are removed.

6. **Exploratory Data Analysis (EDA):**
    - Basic information about the DataFrame is displayed (`watches.info()`).
    - Descriptive statistics are shown (`watches.describe()`).
    - Histogram, boxplot, scatter plot, and bar plot visualizations are created to analyze the distribution and relationships between price and rating.

7. **Identifying Best Watches under Different Price Ranges:**
    - Watches under $5000, $10000, and $20000 are filtered and sorted based on reviews and ratings.
    - The best watch in each category is displayed.

### How to Run:
- Make sure to install the required libraries (`requests`, `pandas`, `matplotlib`, `seaborn`, `beautifulsoup4`) before running the script.
- The script assumes the existence of a `HEADERS` variable, which is not defined in the provided code. You may need to define it with appropriate headers for your web requests.

### Note:
- Web scraping is subject to the terms of service of the website being scraped. Make sure to review and comply with the terms of Amazon or any other website you are scraping.
- The provided code may need adjustments based on the structure of the website, changes in HTML structure, or updates to the website layout.
