# Groceries Data, 2010 - 2025

The files [groceries_Oct_2010.js]() and [groceries_Feb_2025.js]() contains historic grocery prices from 2010 and 2025.

Each row includes the name of the Product, the Year the price was recorded, and the Price and Weight of the product at four stores: Aldi, Kroger, Publix, and Trader Joe's.

There are some additional columns, such as Price/Weight and Comment, that have been included for completeness.

## Data source
This data was compiled by [CompareGroceryPrices.ORG](https://www.comparegroceryprices.org/index.html).

## Data contents and format

The fields relevant to this example are:
* Product: Name of the product, products may have similar names (e.g. "Eggs, cage free" and "Eggs, regular")
* Year: The year in which price and weight data was recorded for a product
* Aldi.Price: Price of product at Aldi
* Aldi.Weight: How much product is provided for the price at Aldi
* Kroger.Price: Price of product at Kroger
* Kroger.Weight: How much product is provided for the price at Kroger
* Publix.Price: Price of product at Publix
* Publix.Weight: How much product is provided for the price at Publix
* Trader Joe's.Price: Price of product at Walmart
* Trader Joe's.Weight: How much product is provided for the price at Walmart

## How to use with ChatGPT

To write a prompt that uses both datasets to make a visualization with this data, simply include the name of each file and a copy of its contents.
For example:

```
I am building a data visualization tool,
and would like you to write the code for me. 

From a technical perspective:
I want a standalone HTML page that I can run locally from my computer.

The data should be loaded by including two Javascript files.
Both files are formatted as comma-separated values (CSV), contained in a Javascript variable.

The first file is groceries_Oct_2010.js
The first few lines look like this:
const groceries_2010 = Product,Aldi.Price,Aldi.Weight,Aldi.Price/Weight,Aldi.Natural,Aldi.Comment,Kroger.Price,Kroger.Weight,Kroger.Price/Weight,Kroger.Natural,Kroger.Comment,Trader Joe's.Price,Trader Joe's.Weight,Trader Joe's.Price/Weight,Trader Joe's.Natural,Trader Joe's.Comment,Publix.Price,Publix.Weight,Publix.Price/Weight,Publix.Natural,Publix.Comment,Year
Aluminum Foil,$2.29,75 sq ft,,,Kwik 'n Fresh,,,,,,,,,,,2.99,50 sq ft,,,Publix,2010
Apple Juice,$1.19,64 fl oz,,,Nature's Nectar,$1.39,64 fl oz,,,Kroger Value,$2.49,64 fl oz,,Y,TJ,$2.49,2 qt,,,"Publix, pure, not from concentrate",2010
Apple Sauce,$0.99,25 oz,,,"Sweet Harvest, regular or cinnamon",$1.92,50 oz,,,"Kroger, classic, cinnamon and no sugar added",$1.99,25 oz,,Y,"TJ, unsweetened",$2.73,46 oz,,Y,"Mott's, no sugar added",2010
[etc.]

The second file is groceries_Feb_2025.js
The first few lines look like this:
const groceries_2016 = const groceries_2025 = Product,Aldi.Price,Aldi.Weight,Aldi.Price/Weight,Aldi.Comment,Kroger.Price,Kroger.Weight,Kroger.Price/Weight,Kroger.Comment,Trader Joe's.Price,Trader Joe's.Weight,Trader Joe's.Price/Weight,Trader Joe's.Comment,Publix.Price,Publix.Weight,Publix.Price/Weight,Publix.Comment,Walmart.Price,Walmart.Weight,Walmart.Price/Weight,Walmart.Comment,Year
Aluminum Foil,$1.99,75 sq ft,,Boulder,$2.49,75 sq ft,,"Kroger, regular strength; best price seen: 1.69 w/ card",,,,,2.45,75 sq ft,,"Publix, regular strength",$2.97,90 sq ft,,Great Value,2025
Apple Juice,$1.69,64 fl oz,,Nature's Nectar,$1.50,64 fl oz,,Kroger Value,$2.99,64 fl oz,,"TJ, regular",$2.69,64 oz,,"Publix Premium, not from concentrate",$2.68,96 fl oz,,"Great Value, from concentrate",2025
Apple Sauce,$1.29,25 oz,,"Sweet Harvest, regular or cinnamon",$2.89,50 oz,,"Kroger, classic, cinnamon and no sugar added",$1.99,25 oz,,"TJ, unsweetened",$2.50,46 oz,,"Mott's, original, no sugar added (natural) or cinnamon",$1.98,48 oz,,"Great Value, original or cinnamon",2025
"Apples, Gala, bag",$2.99,3 lbs,,"Washington apples, various growers",$5.79,5 lbs,,Kroger,$2.99,2 lbs,,Various growers,$4.99,3 lbs,,Various growers,$3.57,3 lbs,,"Washington State, other growers",2025
[etc.]

Build me a line chart comparing product prices in 2010 (first file) versus 2025 (second file).
If a product does not have values in both 2010 and 2025, exclude the product.
Color lines based on whether the price increased, decreased, or stayed the same between 2010 and 2025.
Give each line an opacity of 0.3
The ends of each line should be a point for each product.
Hovering on the line or the point should show a tooltip with the product name.

Also add a search bar at the top to filter by product name.
Add a drop-down to filter by store (Publix, Aldi, Trader Joe's, and Kroger).
The y-axis should re-scale when filtering.
```

## Viewing the visualization

The ChatGPT output in response to the above prompt should be saved in an `index.html` file.
Make sure that this file is in the same folder as `groceries_Oct_2010.js` and `groceries_Feb_2025.js`.
To view the visualization, simply open `index.html` in any browser.