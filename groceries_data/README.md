# Groceries Data, 2010 - 2025

The file [groceries_no_TJ.js](https://wattenberg.github.io/data/groceries_data/groceries_no_TJ.js) contains historic grocery prices from four years (2010, 2016, 2022, and 2025).

Each row includes the name of the Product, the Year the price was recorded, and the Price and Weight of the product at four stores: Aldi, Kroger, Publix, and Walmart.

There are some additional columns, such as Price/Weight and Comment, that have been included for completeness. However, you do not have to work with them for this assignment.

## Task

The data from Trader Joe's has been intentionally omitted from this file.

Imagine that you are a Trader Joe's retail strategist. Your task is to recommend a price for five grocery products given all the data you have on your competitors. For example, you could choose to match the average price across all grocery chains, or undercut everyone with lower prices, or adopt something more complex. You may even choose to use a different strategy for each product.

Whatever your decision, please *1) describe the strategy*, and *2) provide visualizations to explain how your recommended product prices were derived from the chosen strategy.*

The five grocery items are:

* Coffee
* Eggs, regular
* Oil, Olive, extra virgin
* Tomato Sauce
* Product of your choice

2025 prices may have changed since we downloaded the data some months ago. We ask that you take the provided data as ground truth and avoid looking up prices at your local Trader Joe's.

Your recommendations will not be judged against the actual Trader Joe's prices. For those interested, we will release the Trader Joe's data at the end of this homework.

## Data source
This data was compiled by [CompareGroceryPrices.ORG](https://www.comparegroceryprices.org/index.html).

## Data contents and format

This is a special format designed to be easy to use for a Javascript program that can be run from your own computer's file system.
It is essentially putting a comma-separated table into a Javascript variable. The table itself looks like this:
```
const groceries_data=`Product,Year,Aldi.Price,Aldi.Weight,Aldi.Price/Weight,Aldi.Natural,Aldi.Comment,Kroger.Price,Kroger.Weight,Kroger.Price/Weight,Kroger.Natural,Kroger.Comment,Publix.Price,Publix.Weight,Publix.Price/Weight,Publix.Natural,Publix.Comment,Walmart.Price,Walmart.Weight,Walmart.Price/Weight,Walmart.Comment
Aluminum Foil,2010,$2.29,75 sq ft,,,Kwik 'n Fresh,,,,,,2.99,50 sq ft,,,Publix,,,,
Apple Juice,2010,$1.19,64 fl oz,,,Nature's Nectar,$1.39,64 fl oz,,,Kroger Value,$2.49,2 qt,,,"Publix, pure, not from concentrate",,,,
Apple Sauce,2010,$0.99,25 oz,,,"Sweet Harvest, regular or cinnamon",$1.92,50 oz,,,"Kroger, classic, cinnamon and no sugar added",$2.73,46 oz,,Y,"Mott's, no sugar added",,,,
[etc.]
```
The fields relevant to this task are:
* Product: Name of the product, products may have similar names (e.g. "Eggs, cage free" and "Eggs, regular")
* Year: The year in which price and weight data was recorded for a product
* Aldi.Price: Price of product at Aldi
* Aldi.Weight: How much product is provided for the price at Aldi
* Kroger.Price: Price of product at Kroger
* Kroger.Weight: How much product is provided for the price at Kroger
* Publix.Price: Price of product at Publix
* Publix.Weight: How much product is provided for the price at Publix
* Walmart.Price: Price of product at Walmart
* Walmart.Weight: How much product is provided for the price at Walmart

## How to use with ChatGPT

Here's a prompt that provides a starting point for making a visualization with this data.
It creates a simple line chart visualization of Aluminum Foil prices.

```
I am building a data visualization tool,
and would like you to write the code for me. 

From a technical perspective:
I want a standalone HTML page that I can run locally from my computer.

The data should be loaded by including this Javascript file: 
https://wattenberg.github.io/data/groceries_data/groceries_no_TJ.js
It is formatted as comma-separated values (CSV), contained in a Javascript variable;
the first few lines look like this:

const groceries_data=`Product,Year,Aldi.Price,Aldi.Weight,Aldi.Price/Weight,Aldi.Natural,Aldi.Comment,Kroger.Price,Kroger.Weight,Kroger.Price/Weight,Kroger.Natural,Kroger.Comment,Publix.Price,Publix.Weight,Publix.Price/Weight,Publix.Natural,Publix.Comment,Walmart.Price,Walmart.Weight,Walmart.Price/Weight,Walmart.Comment
Aluminum Foil,2010,$2.29,75 sq ft,,,Kwik 'n Fresh,,,,,,2.99,50 sq ft,,,Publix,,,,
Apple Juice,2010,$1.19,64 fl oz,,,Nature's Nectar,$1.39,64 fl oz,,,Kroger Value,$2.49,2 qt,,,"Publix, pure, not from concentrate",,,,
Apple Sauce,2010,$0.99,25 oz,,,"Sweet Harvest, regular or cinnamon",$1.92,50 oz,,,"Kroger, classic, cinnamon and no sugar added",$2.73,46 oz,,Y,"Mott's, no sugar added",,,,
[etc.]

The fields are:
* Product: Name of the product, products may have similar names (e.g. "Eggs, cage free" and "Eggs, regular")
* Year: The year in which price and weight data was recorded for a product
* Aldi.Price: Price of product at Aldi
* Aldi.Weight: How much product is provided for the price at Aldi
* Kroger.Price: Price of product at Kroger
* Kroger.Weight: How much product is provided for the price at Kroger
* Publix.Price: Price of product at Publix
* Publix.Weight: How much product is provided for the price at Publix
* Walmart.Price: Price of product at Walmart
* Walmart.Weight: How much product is provided for the price at Walmart

The visualization should show a line chart of how the price of Aluminum Foil has changed over the years.
Create a separate line for each store: Aldi, Kroger, Publix, and Walmart. Use a categorical color scheme.
Add numerical labels to the lines to include the price and weight of the aluminum foil for each store in each year.
```