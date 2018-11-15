# My Blog
#### How it works:



1.  Setup webdriver and proxy. 
    1.  Full browser session seems to be required in order to get full search results
    1.  Proxy required to programmatically extract the cach_key, which is also required for full search results
1.  Login to instacart with generic credentials
1.  Change zip code as determined by input data, called search_ref via clicking through interface
1.  Change store to target store for scrape, e.g. whole-foods, requires instacart version of the store name
1.  Extract cach_key from har file generated from network traffic now that we have logged in, set the zip code and set the store
1.  Loop through keywords, now that we have the required web session and cach_key, and download json provided by instacart for each search
1.  Extract list of instacart's product_ids for each search
1.  Dedupe dataframe of products and create list of all search terms that each product_id was found under, e.g. "Boar's Head Ham Sandwich" found under search terms ['ham', 'sandwich']
1.  For each product_id hit the product details instacart endpoint and download the product details json (includes ingredients, nutrients, warehouse_id, aisle_id)
1.  Parse product details json for product name (which includes the brand name not clear where the brand name ends and product name begins), ingredients, and nutrient info. Also parse warehouse_id and aisle_id in order to get brands names
1.  In order to get the brand names, we first create a unique list of aisles to loop through, unfortunately the only way to pick up the brand names is by grabbing the brand name filters that exist in the aisle page json. 
1.  With the list of unique aisles we download the json from each page's endpoint
1.  For each of the above we extract the list of brand names 
1.  With both product and brand per aisle info we must merge our list of brands per aisles back into the product dataframe 
1.  For matching products to brand we first try to match brands as a perfect substring match in each product title, next we try to match with the full list of brands from the store
