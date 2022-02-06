# financial_planning_tools
Financial tool for emergencies and retirement planning. This project builds a tool to help credit union members evaluate their financial health. The credit union member should be able to assess their monthly budgets and forecast a reasonably effective retirment plan based on their current holdings of cryptocurrencies, stocks, and bonds. The project creates two financial analysis tools:
1. A financial planner for emergenices. Members will be able to use the tool to visualize their current savings and determine if they have enough reserves for an emergency.
2. A financial planner for retirement. This will forecast the performance of their retirement portfolio in 30 years. To do this, the tool will make an Alpaca API call via the Alpaca SDK to get historical price data to use in Monte Carlo simulations. Additionally, will forecast cumulative returns in ten years to find out if changes to the member's portfolio will them to retire earlier. 

---

## Technologies

This project uses the following libraries and dependencies:
+ **Anaconda**: an open source package and environment management system.
+ **JupyterLab**: an extensive environment using web-based user interface designed for data analysis. 
+ **Pandas**: (included in Anaconda) a Python package data analysis toolkit.
+ **matplotlib inline**: library to create static, animated, and interactive visualizations in JupyterLab.
+ **OS**: The OS module comes under Python's standard utility models and provides functions for interacting with the computer's operating system. The OS module does not require a separate download.

This Python modules and libraries are needed to facilitate API Request:
+ **Requests**: The Python Requests library helps access data via APIs.
+ **JSON**: This library puts the response (the data) from an API into a human-readable format. 
+ **Alpaca API**: Python library for the Alpaca Commission Free Trading API. Allows rapid trading algo development easily, with support  for both REST and streaming data interfaces.

---

## Installation Guide

Check to ensure that Jupyterlab is installed on your machine by entering the following into your environment:
```
pip install -c anaconda requests
pip install -c jmcmurray json
pip install python-dotenv
pip install alpaca-trade-api
```
### Verify Installations 

In the terminal, activate the Conda development environment, and run the following codes to verify the installs:
```
conda list requests

conda list json

pip list | grep -E "python-dotenv|alpaca-trade-api"
```

## Get the API Keys

To run this project, you would need **API Keys**, more specifically **Alpaca API and Secret Keys**. These are unique identifiers needed for authentication for trading. To get your API credentials, you can go to [Alpaca Markets sign-up page](https://app.alpaca.markets/signup) and set-up or login to generate your keys. 

Once logged in, click on "Go to Paper Account" on the left hand panel:
<img width="702" alt="image" src="https://user-images.githubusercontent.com/96001018/152703809-76a7dafe-954b-4636-86ea-d5e2f9846f09.png">

Click on the right hand panel to view your key or generate new keys. You will need both API Keys and Secret Keys for this project. 
<img width="698" alt="image" src="https://user-images.githubusercontent.com/96001018/152703866-56f18590-4676-4703-b19f-4a2e76bdc395.png">

---

## Usage 
Import the required libraries and dependencies:

<img width="270" alt="image" src="https://user-images.githubusercontent.com/96001018/152704870-6da679db-7da5-4970-b6a7-4581d86ccc62.png">

### Create a Financial Planner for Emergencies

**Evaluate the Cryptocurrency Wallet by Using Requests Library**
Determined the current value of the credit union member's cryptocurrency wallet, consist of Bitcoin (BTC) and Ethereum (ETH) cryptocurrencies by using the Python Requests library. 
<img width="387" alt="image" src="https://user-images.githubusercontent.com/96001018/152704988-e12d599e-8adc-4130-ac7b-13547e28a3a8.png">

URLs for the API calls to Free Crypto API in order to get current pricing information on member's crytpocurrencies.
<img width="590" alt="image" src="https://user-images.githubusercontent.com/96001018/152705481-7faf655a-626a-475e-a529-a5f3987d9e78.png">

Example of making an API call to access the current price of BTC by using the Python requests library. Performed the same request for ETH.
<img width="298" alt="image" src="https://user-images.githubusercontent.com/96001018/152705185-c2462399-e374-4377-aa5d-e00a621ac425.png">

Calculate the value of the current amount of each cryptocurrency and of the entire cryptocurrency wallet.
<img width="347" alt="image" src="https://user-images.githubusercontent.com/96001018/152705022-cf1bf277-8319-49d1-be80-620a0614cb6b.png">

**Evaluate the Stock and Bond Holdings by Using the Alpaca SDK**
Make an API call via Alpaca SDK to get the current closing prices of the SPDR S&P 500 ETF Trust (ticker:SPY) and iShares Core US Aggregate Bond ETF (AGG). 

Using an environment file (```.env```) to store values of user's Alpaca API key and secret key. 
<img width="428" alt="image" src="https://user-images.githubusercontent.com/96001018/152705829-1dcf1ecc-37a3-4e80-b763-436677499f10.png">



Determined the composition of the member's portfolio and created a pit chart visualization. 

<img width="296" alt="image" src="https://user-images.githubusercontent.com/96001018/152705922-2f2dd5b1-89e5-4f75-9c04-1fe7f74c8340.png">


Using Monte Carlo simulation to forecast 30 year simulation of a 60/40 stock and bond portfolio. Visualizations were created to plot 500 simulations of cumulative returns trajectories over the 30 years (or 2520 trading days) and a histogram shows the shows the distribution of cumuluative returns across 500 simulations. 

<img width="394" alt="image" src="https://user-images.githubusercontent.com/96001018/152705946-12f180d3-d12f-48b8-be1d-3f5aed0ab5c8.png">

<img width="359" alt="image" src="https://user-images.githubusercontent.com/96001018/152705957-4aea4484-4bfa-4529-a9a0-5e2a7cb4ae67.png">

<img width="278" alt="image" src="https://user-images.githubusercontent.com/96001018/152705966-f63b4310-dd7d-4cd9-b8a5-f43bfb69e537.png">


Similar to the process of the 30 year simulation, performed a 10 year simulation of a 80/20 portfolio with a more heavily weighted stock option.
<img width="447" alt="image" src="https://user-images.githubusercontent.com/96001018/152705977-386d799d-4177-4cd2-b4a5-cda223a1b46c.png">

<img width="271" alt="image" src="https://user-images.githubusercontent.com/96001018/152705997-05f0e6c6-9cce-4706-a72d-7e3ff7525ac9.png">

<img width="337" alt="image" src="https://user-images.githubusercontent.com/96001018/152706014-ec5ee253-e5d7-4743-889f-f5cc7610f904.png">



---

## Contributors

Leigh Anne Badua leighbadua@gmail.com 

---

## License

+ [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/)
