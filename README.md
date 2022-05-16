The data used for this project is from Kaggle and can be viewed here:https://www.kaggle.com/gabrielramos87/an-online-shop-business

Context:
The primary aim of this project is to perform exploratory data analysis in the given data.
The following are used to get a better understanding of the data:
- Spark SQL
- Pandas
- Plotly

I used Google Colaboratory for this project.

About the data [from Kaggle]:

This is a dataset of UK-based B2C e-commerce sales transactions for one year. This London-based shop has been selling gifts and homewares for adults and children through the website since 2007. Their customers come from all over the world and usually make direct purchases for themselves. There are also small businesses that buy in bulk and sell to other customers through retail outlet channels.
The dataset contains 500K rows and 8 columns. The following is the description of each column.

TransactionNo (nominal): a six-digit unique number that defines each transaction. The letter “C” in the code indicates a cancellation.
Date (numeric): the date when each transaction was generated.
ProductNo (nominal): a five or six-digit unique character used to identify a specific product.
Product (nominal): product/item name.
Price (numeric): the price of each product per unit in pound sterling (£).
Quantity (numeric): the quantity of each product per transaction. Negative values related to cancelled transactions.
CustomerNo (nominal): a five-digit unique number that defines each customer.
Country (nominal): name of the country where the customer resides.

Analysis:

The data is first anaysed using spark SQL to get a basic idea of how the data is:
![Spark-Sales](https://user-images.githubusercontent.com/53789918/155854138-59324f23-3ac6-48da-8989-6a10a3457e6e.JPG)


Pandas:

The data is later converted to a dataframe and using groupby and aggregate functions, the data is further sorted and filtered to identify the daily transactions, The customers for the business per day, how many orders are cancelled per day and which products are cancelled the most.

![Daily customers](https://user-images.githubusercontent.com/53789918/155854132-3bba0c1f-cff7-4afe-b505-bd5d2a9e9e53.JPG)
![Daily transaction](https://user-images.githubusercontent.com/53789918/155854134-4998a40e-0515-4a01-881d-1d941907ed99.JPG)
![Cancelled products](https://user-images.githubusercontent.com/53789918/155854129-bf5dadb6-0016-4d62-ad1c-00bbe6037eff.JPG)

These data are later visualized using plotly to get a much better understanding:

First, the number of customers daily and the number of transactions per day are plotted. We can see that there is only a minor difference between them. So we can safely say, most visit does turn into a transaction. So the customers do try to purchase from the website.

![Daily trans - plotly](https://user-images.githubusercontent.com/53789918/155854133-779e1d46-470f-4f0d-a896-2bfaaa4fe7e5.JPG)
![Daily cust - plotly](https://user-images.githubusercontent.com/53789918/155854130-335ef6ee-e36c-4208-8ce4-f66c0525a329.JPG)

Cancellations:

Since the transactions also invloves the cancelled ones, we take a much closer look at the cancelled orders to see if it is a cause of failure. The cancellations per day are plotted.
And we can see in a considerable amount of times, the number of cancellations were as much as the customers that day. So we dig in deeper and find the products that are cancelled the most.

![Cancellation per day - plotly](https://user-images.githubusercontent.com/53789918/155854128-944503eb-e872-44d7-8312-6dd79822b6bc.JPG)

We can see there are two major products that are cancelled the most. This is an alarming number in comparison with the other products given by the business.
![most cancelled](https://user-images.githubusercontent.com/53789918/155854136-458cd9c4-0858-4ddd-9f23-8d4f64164d28.JPG)


A basic exploratory data analysis has given much further insights than we started with. The cancellations, if fixed, can yield a much higher profit for the business. So by analysing the two most cancelled items, the issues can be rectified.
