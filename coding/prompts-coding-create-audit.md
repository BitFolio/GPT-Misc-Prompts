# General help with coding audits

## System
```
You are an expert Python coder. You are a senior software engineer
```

## Avoid partial code print
```
Write out the entire code with your change.
```

## Check the code and improve it
```
The following is code intented for this task.
Check the code carefuly for correctness, style and efficiency and improve it.
```

## Audit the code
```
Audit the following code. Check the code carefuly for correctness, style and efficiency.
```

## Complete example
```
Using python, write an application that will (1) read a json file (binance.json) and parse the file, (2) the contents of the json file is in the format of [{"description":"Binance RGT/USDT","displaySymbol":"RGT/USDT","symbol":"BINANCE:RGTUSDT"},{"description":"Binance WABI/BTC","displaySymbol":"WABI/BTC","symbol":"BINANCE:WABIBTC"}], (3) loop over the contents of the file, (4) for each symbol, do an api call (GET) to "https://finnhub.io/api/v1/quote?symbol=" passing the following api key in the header "X-Finnhub-Token: co357777777777" (5) the api will return JSON data in the format of "{"c":71030,"d":1262.92,"dp":1.8102,"h":71227.22,"l":69540,"o":69767.08,"pc":69767.08,"t":1711838091}". Below are the mappings:
c = price
d = change
dp = percent_change
h = high
l = low
o = open
pc =previous_close
t = unix timestamp
(6) Write the data to the followng mysql database table:
CREATE TABLE `admin_admin_blog_bitfolio`.`binance_history` (
  `date` DATE NOT NULL,
  `symbol` VARCHAR(25) NOT NULL,
  `description` VARCHAR(30) DEFAULT NULL,
  `display_symbol` VARCHAR(25) DEFAULT NULL,
  `price` FLOAT DEFAULT NULL,
  `change` FLOAT DEFAULT NULL,
  `percent_change` FLOAT DEFAULT NULL,
  `high` FLOAT DEFAULT NULL,
  `low` FLOAT DEFAULT NULL,
  `open` FLOAT DEFAULT NULL,
  `previous_close` FLOAT DEFAULT NULL,
  `volume` BIGINT DEFAULT NULL,
  PRIMARY KEY (`date`, `symbol`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
volume will be null.
Use sqlalchemy.
```

## Another example
```
Using PHP, write an application that will (1) expose a JSON data feed or api, (2) require an API key to access the JSON data feed, (3) the API key will be read from a file (config.ini), (4) config.ini will also contain database connection info and the name of the log file, (5) the endpoint to expose is "/quotes.php?symbol='BINANCE:BTCUSD'" where "symbol" is the particular coin, (5) this endpoint will return all price quote data from a mysql database table (coin_history) for a particular coin for yesterday's date, (6) the application will log each query in a logfile named "logs/quote_history.log", (7) the database table for "coin_history" is as follows:
USE admin_admin_blog_bitfolio;
CREATE TABLE coin_history (
  Date DATE,
  Coin TINYTEXT,
  Open FLOAT,
  High FLOAT,
  Low FLOAT,
  Close FLOAT,
  Volume FLOAT,
  `Market Cap` FLOAT,
  PRIMARY KEY (Date, Coin(14))
);

```

