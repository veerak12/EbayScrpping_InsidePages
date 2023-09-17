# EbayScrpping_InsidePages

This code essentially scrapes product data for speakers from eBay by iterating through the specified number of pages, extracting the relevant information from each product page, and saving the data to a CSV file.

The code defines a function called scrape_ebay_speakers that takes two parameters: url (the base URL of eBay) and num_pages (the number of pages to scrape).

Inside the function, an empty list called product_links is created to store the links of the products to be scraped.

A loop is initiated to iterate through the specified number of pages (from 1 to num_pages).

Inside the loop, a GET request is made to the specified eBay URL with the search parameters for speakers and the page number. The response is stored in the variable r.

The HTML content of the response is parsed using BeautifulSoup, and all the product links are extracted using the appropriate CSS selector. The links are then appended to the product_links list.

After scraping all the product links, an empty list called product_list is created to store the scraped product data.

Another loop is initiated to iterate through each product link in the product_links list.

Inside the loop, a GET request is made to each product link, and the HTML content of the response is parsed using BeautifulSoup.

Various product information such as the product name, price, seller information, shipping charges, eBay product number, and total reviews are extracted from the parsed HTML using appropriate CSS selectors. If any information is not found, a default value of 'None' is assigned.

The extracted product information is stored in a dictionary called product_data.

The product_data dictionary is appended to the product_list.

Once all the product links have been processed, the product_list is used to create a pandas DataFrame called df.

The DataFrame is then saved to a CSV file named "Ebay_Speakers.csv" using the to_csv method.

Finally, the function returns the DataFrame df.

An example usage of the function is provided at the end, where the function is called with the specified eBay URL and the number of pages to scrape. The returned DataFrame is stored in the variable data, and the first 10 rows of the DataFrame are printed using the head(10) method.
