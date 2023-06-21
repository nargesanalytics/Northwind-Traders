# Northwind-Traders
It contains a dataset of Northwind Traders visualized by Power BI and includes various reports
This is Sales & order data, including information on customers, products, orders, shippers, and employees for Northwind Traders, 
a global food supply company that specializes in supplying gourmet food products to restaurants, cafes,
and food retailers around the world.



## Table of Contents
* [Introduction](#Introduction)
* [Dashboard Requirements](#Dashboard-Requirements)
* [Installation / Usage](#Installation--Usage)
* [DAX Formulas Used in Measures](#DAX-Formulas-Used-in-Measures)
* [Offers]


* [Introduction](#Introduction)
As their data analyst, I have been tasked with building a top-level KPI dashboard for the stakeholders and Executive Team.
This dashboard would give the company's Executives insights into the company's sales performance. 
Some of the insights are:

   - Total order count
   - Total order value
   - Average order size
   - Frequency of orders per customer
   - High-value orders
   - Customer segmentation analysis
   - Employee performance metrics
   - 
* The dataset can be accessed from this link:(https://www.mavenanalytics.io/data-playground)

## Installation / Usage
* Install Power BI Desktop from Official [Power BI Download Site](https://powerbi.microsoft.com/en-us/downloads/)
* Download data files from link given in Introduction
* Clone/download this repository to your local machine
* Open Dashboard report file (analyize.pbix) in Power BI Desktop, to access the dashboard's interactivity 

## DAX Formulas Used in Measures
**1.Total Order Value:
 orderValue = SUM(order_details[lineItemSubtotal])
 
**2.High-Value Orders:
* HighValueOrderValue = CALCULATE(SUMX(order_details, order_details[unitPrice] * order_details[quantity]),customers[CustomerType] = "HighValue")

**3.Average Order Size
(a) Average Order Size = order_details[TotalOrderValue] / order_details[TotalOrderCount]
(b) Goal Achievement = IF(order_details[Average Order Size] >= [Target Average Order Size], "Achieved", "Not Achieved")
(c)Target Average Order Size = 100

**4.Frequency of Orders per Customer
* OrderCount = CALCULATE(COUNT('orders'[orderID]), ALLEXCEPT('orders', 'orders'[customerID]))

**5.Customer Segmentation Analysis
(a) CustomerGroup = 
SWITCH(TRUE(),
    'customers'[CustomerID] IN {"ALFKI", "ANATR", "ANTON", "AROUT", "BERGS"}, "Group A",
    'customers'[CustomerID] IN {"BLAUS", "BLONP", "BOLID", "BONAP", "BOTTM"}, "Group B",
    'customers'[CustomerID] IN {"BSBEV", "CACTU", "CENTC", "CHOPS", "COMMI"}, "Group C",
    'customers'[CustomerID] IN {"CONSH", "DRACD", "DUMON", "EASTC", "ERNSH"}, "Group D",
    'customers'[CustomerID] IN {"FAMIA", "FISSA", "FOLIG", "FOLKO", "FRANK"}, "Group E",
    'customers'[CustomerID] IN {"FRANR", "FRANS", "FURIB", "GALED", "GODOS"}, "Group F",
    'customers'[CustomerID] IN {"GOURL", "GREAL", "GROSR", "HANAR", "HILAA"}, "Group G",
    'customers'[CustomerID] IN {"HUNGC", "HUNGO", "ISLAT", "KOENE", "LACOR"}, "Group H",
    'customers'[CustomerID] IN {"LAMAI", "LAUGB", "LAZYK", "LEHMS", "LETSS"}, "Group I",
    'customers'[CustomerID] IN {"LILAS", "LINOD", "LONEP", "MAGAA", "MAISD"}, "Group J",
    'customers'[CustomerID] IN {"MEREP", "MORGK", "NORTS", "OCEAN", "OLDWO"}, "Group K",
    'customers'[CustomerID] IN {"OTTIK", "PARIS", "PERIC", "PICCO", "PRINI"}, "Group L",
    'customers'[CustomerID] IN {"QUEDE", "QUEEN", "QUICK", "RANCH", "RATTC"}, "Group M",
    'customers'[CustomerID] IN {"REGGC", "RICAR", "RICSU", "ROMEY", "SANTG"}, "Group N",
    'customers'[CustomerID] IN {"SAVEA", "SEVES", "SIMOB", "SPECD", "SPLIR"}, "Group O",
    'customers'[CustomerID] IN {"SUPRD", "THEBI", "THECR", "TOMSP", "TORTU"}, "Group P",
    'customers'[CustomerID] IN {"TRADH", "TRAIH", "VAFFE", "VICTE", "VINET"}, "Group Q",
    'customers'[CustomerID] IN {"WANDK", "WARTH", "WELLI", "WHITC", "WILMK"}, "Group R",
    'customers' [CustomerID] IN {"WOLZA"}, "Group S",
    
    "Other"
)
(b)TotalOrderValue = SUMX(order_details, order_details[unitPrice] * order_details[quantity])

**6.Employee Performance Metrics
(a) Target = 50
(b) TotalOrderValue = SUMX(order_details, order_details[unitPrice] * order_details[quantity])


## Offers:
1)Considering the good performance of the employees in America and by creating satisfaction and better facilities for these people,
it can be predicted that the process of penetration in the American markets will be easy in a few years, so the creation of a professional human resources team and 
the necessary training for the development process The individual and career of this group will have a better upward trend ahead.

2)Considering the type of products needed and necessary in European countries based on the high volume of orders in these countries,
we will witness the creation of a research and development group to identify and localize products that will help double sales in these
regions in the coming years.

3)Also, due to the amount of orders and the distance of the destination from the factories, it creates a downward trend and
even slowness in sending orders, which can be reduced with the necessary procurement, including investment in different farms in
countries that have a suitable platform for this profession. transportation and also creating jobs in native countries saw the trend of
sales growth and customer satisfaction in the near future.

