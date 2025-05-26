# Crypto Correlation & Clustering

This project fetches two years of daily price data for the top 20 USDT-paired cryptocurrencies from Binance, computes returns, correlation matrices, hierarchical clusters (Ward’s method), and visualizes the results using Riskfolio.

Please see image file for the output!

## Methodology & Insights

This project applies **hierarchical clustering** using **Ward’s linkage method** to explore the interdependence among major cryptocurrencies based on their daily returns over the past two years.

### Why This Approach?

- **Correlation analysis** helps identify how strongly assets move together, which is essential for portfolio diversification and risk management.
- **Hierarchical clustering** groups assets into similarity-based clusters without requiring the number of clusters to be predefined.
- **Ward's method** minimizes within-cluster variance, producing interpretable, compact clusters ideal for financial time-series data.

### What Do the Results Tell Us?

- The **correlation matrix** highlights which assets tend to behave similarly — for example, high correlations between coins in the same ecosystem (e.g., ETH–MATIC or BTC–LTC).
- The **dendrogram** visually reveals natural groupings of cryptocurrencies. Assets with similar volatility patterns and market behavior cluster together.
- The **heatmap** provides an intuitive way to spot tightly correlated groups and potential diversification opportunities.

This clustering framework offers a valuable foundation for further portfolio construction, stress testing, or building systematic trading strategies based on co-movement and regime detection.




## Features

- Secure API keys via a `.env` file (`python-dotenv`)  
- Data ingestion from Binance REST API (`python-binance`)  
- Data cleaning & alignment into a single pandas DataFrame  
- Return calculations: daily % changes & median returns  
- Correlation analysis: Pearson correlation matrix  
- Hierarchical clustering: Euclidean distance + Ward linkage  
- Visualization: Clustered correlation heatmap & dendrogram via `rp.plot_clusters`

## Installation

1. Clone this repository  
   ```bash
   git clone https://github.com/yourusername/crypto-correlation-clustering.git
   cd crypto-correlation-clustering

2. Copy and configure the environment file
cp .env.example .env

Open .env and fill in your real Binance keys.

3. Install Python dependencies

## Usage

1. python fetch_data.py

2. The script will

3. load keys from .env,

4. download 2 years of daily candles for the 20 coins,

5. clean & align the data,

6. compute returns, median returns, a correlation matrix,

7. print stats + Ward linkage to the console,

8. show a clustered correlation heat-map with dendrogram.

## Repository Layout

.
├── .env.example      ← sample env file (do **not** commit your real .env)
├── .gitignore        ← ignore rules
├── LICENSE           ← MIT licence
├── README.md         ← you are here
├── fetch_data.py     ← main script
└── requirements.txt  ← Python deps

## Dependencies

Dependencies are listed in `requirements.txt`.

*python-dotenv

*python-binance

*pandas

*seaborn

*scipy

*riskfolio-lib

*matplotlib

## License

This project is licensed under the MIT License. See LICENSE for full details.