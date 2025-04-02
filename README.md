# CoinMarket

A Python-based cryptocurrency tracking and analysis application that leverages the CoinMarketCap API to monitor real-time cryptocurrency data, store it over time, and visualize market trends.

## Features

- Real-time cryptocurrency market data retrieval via CoinMarketCap API
- Automated data collection at configurable intervals
- Historical price and market metric tracking
- Percentage change analysis (1h, 24h, 7d, 30d, 60d, 90d)
- Visual trend analysis with customizable graphs
- CSV data export for further analysis

## Requirements

- Python 3.6+
- pandas
- seaborn
- matplotlib
- requests
- json
- time
- datetime
- csv

## Installation

1. Clone the repository:
   ```
   git clone https://github.com/SeyiDan/CoinMarket.git
   cd CoinMarket
   ```

2. Install required packages:
   ```
   pip install pandas seaborn matplotlib requests
   ```

3. Obtain a CoinMarketCap API key from [CoinMarketCap](https://coinmarketcap.com/api/)

4. Replace the API key in the code with your own key:
   ```python
   headers = {
     'Accepts': 'application/json',
     'X-CMC_PRO_API_KEY': 'YOUR_API_KEY_HERE',
   }
   ```

## Usage

### Basic Tracking
Run the main script to collect current cryptocurrency data:


### Scheduled Monitoring
To collect data at regular intervals (e.g., every hour):

```python
# The script will run continuously and collect data every 60 seconds
# Edit the sleep() value to adjust collection frequency
```

### Data Analysis

The script automatically normalizes the data into a pandas DataFrame for analysis:

```python
# Example: Get the current Bitcoin price
current_bitcoin_price = df[df['name'] == 'Bitcoin']['quote.USD.price'].values[0]
```

### Visualization

Create visual representations of cryptocurrency trends with the built-in visualization functions:

```python
# Create a point plot of percentage changes for all tracked cryptocurrencies
sns.catplot(x='percent_change', y='values', hue='name', data=df7, kind='point')
```

## Data Structure

The application collects and stores the following data points for each cryptocurrency:

- Name and symbol
- Current price in USD
- Market capitalization
- Trading volume (24h)
- Circulating and total supply
- Percentage changes (1h, 24h, 7d, 30d, 60d, 90d)
- Timestamp of data collection

## Customization

You can modify the number of cryptocurrencies tracked by changing the 'limit' parameter:

```python
parameters = {
  'start':'1',
  'limit':'15',  # Change this value to track more/fewer cryptocurrencies
  'convert':'USD'
}
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Disclaimer

This application is for educational and informational purposes only. Cryptocurrency investments are volatile and risky. Always do your own research before investing.
