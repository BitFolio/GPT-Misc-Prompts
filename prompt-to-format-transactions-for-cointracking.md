# Prompt to format transactions for cointracking.info

## System
```
You are a crytocurrency expert.
```

## User input
```
Format crypto trades to Excel file. Read the txt files and convert and reformat the file data to a CSV file. The input file names are in the format of YYYY-MM-DD-trading-investing.txt. Each file contains the activity on a single day. Given the data in the provided input files, reformat the text file data to a CSV file. Omit any analysis or commentary. Output the CSV file in the requested format.
Format the CSV output according to the following rules:
- The header must follow the precise format and order of: "Type","Buy Amount","Buy Cur.","Sell Amount","Sell Cur.","Fee Amount (optional)","Fee Cur. (optional)","Exchange (optional)","Trade Group (optional)","Comment (optional)","Date","Liquidity pool (optional)","Tx-ID (optional)","Buy Value in Account Currency (optional)","Sell Value in Account Currency (optional)"
- An example of a row: "Trade",1.5,"BTC",400,"USD",0.8,"USD","Poloniex","Polo Sub Account 1","My first trade",30-01-2018 15:20:25,,,,
- Another example of a row: "Withdrawal",,,0.4,"ETH",0.0035,"ETH","blockchain.com",,"OUT (Transfer)",02-11-2019 17:00:46,,,,
- A third example of a row: "Remove Liquidity",0.01,"ETH",,,,,"MyEtherWallet",,"IN",02-11-2019 17:00:46,"Uniswap V3",,,
- The (optional) fields can be omitted by providing an empty field, e.g., ",,,"
- If there is no data for a required field, the field can be omitted by providing an empty field, e.g., ",,".
- Take great care to count the fields so that each row has the proper number of fields.
- Use double quotes (") as a string delimiter.
- "Type" means type of action, e.g., Trade, Withdrawal, Deposit, Remove Liquidity...
- "Buy Cur." means buy currency. Example currencies are BTC, ETH, MATIC...
- "Sell Cur." means the sell currency. Examples of sell currencies are USD, USDT, ETH, MATIC...
- For the "Trades" type, always try to find values for both "Buy Amount" and "Sell Amount". Hint: For USDT, the "Buy Amount" is the same value as "Buy Value in Account Currency".
- A "Withdrawal" type should always be placed in the fields: "Sell Amount" and "Sell Cur."
- The Date field must be formatted as: "DD-MM-YYYY HH:MM:SS"
```
