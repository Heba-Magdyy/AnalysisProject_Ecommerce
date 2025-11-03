# E-commerce Data Cleaning and RFM Analysis

This project focuses on cleaning and analyzing a transnational e-commerce dataset. The primary goal is to perform a Recency, Frequency, and Monetary (RFM) analysis to segment customers and identify key customer groups.

## Dataset

The dataset contains transactional data from a UK-based online retail company. The following columns are included in the `data.csv` file:

- **InvoiceNo**: A 6-digit invoice number uniquely assigned to each transaction. If this code starts with the letter 'c', it indicates a cancellation.
- **StockCode**: A 5-digit product code uniquely assigned to each distinct product.
- **Description**: The name of the product.
- **Quantity**: The number of units of a product per transaction.
- **InvoiceDate**: The date and time when each transaction was generated.
- **UnitPrice**: The price per unit of a product in sterling.
- **CustomerID**: A 5-digit customer number uniquely assigned to each customer.
- **Country**: The name of the country where each customer resides.

## Data Cleaning

The raw data is processed through the following cleaning steps:

- **Handling Missing Values**: Rows with missing `CustomerID` values are removed, and missing `Description` values are filled with "Unknown Product".
- **Removing Invalid Entries**: Transactions with a negative `Quantity` (indicating cancellations) and a `UnitPrice` of zero are removed.
- **Creating a TotalPrice Column**: A new column, `TotalPrice`, is calculated by multiplying `Quantity` and `UnitPrice`.
- **Converting Data Types**: The `CustomerID` is converted to an integer type, and `InvoiceDate` is converted to a datetime format.

## RFM Analysis

RFM analysis is used to segment customers based on their purchasing behavior. The three metrics are calculated as follows:

- **Recency**: The number of days between a customer's last purchase and a snapshot date (defined as one day after the latest invoice date in the dataset).
- **Frequency**: The total number of unique invoices for each customer.
- **Monetary**: The total amount of money spent by each customer.

## Tools and Libraries

The following tools and libraries were used in this project:

- **Python**: The primary programming language for data analysis.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **Matplotlib and Seaborn**: For data visualization.
- **Jupyter Notebook**: For interactive data analysis and visualization.

## How to Run the Project

To run this project, follow these steps:

1. **Clone the repository**: `git clone <repository-url>`
2. **Install the required libraries**: `pip install pandas numpy matplotlib seaborn jupyter`
3. **Launch Jupyter Notebook**: `jupyter notebook`
4. **Open and run the notebook**: Open the `ecommerce_data_cleaning.ipynb` file and run the cells sequentially.
