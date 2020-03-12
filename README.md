# ELKstack-Bitcoin
Visualizing historical data of Bitcoin using ELK (Elasticsearch, Logstash, Kibana) Stack

## Install 
* Services
```
brew tap gapple/services
```

* ELK on Mac OS X using Homebrew
```
brew install elastic-search
brew install kibana
brew install logstsh
```

## Dataset
* Data: Bitcoin USD (BTC-USD), CCC - CryptoCompare.
* Time Period of the data: Mar 10, 2013 - Mar 10, 2019
* Currency: USD
* Frequency: Daily
* dataset from: https://finance.yahoo.com/quote/BTC-USD/history?period1=1362902400&period2=1552204800&interval=1d&filter=history&frequency=1d

## Configuring Logstash
ref: https://www.elastic.co/guide/en/logstash/current/configuration-file-structure.html
```
# This is a comment. You should use comments to describe
# parts of your configuration.
input {
  ...
}

filter {
  ...
}

output {
  ...
}
```

## Setup and Run ELK
```
# run elasticsearch
elasticsearch
# check if elasticsearch is running on local: http://127.0.0.1:9200/ 
```
```
# insert the data
export TIME_PERIOD="03102013-03102019"
logstash -f "logstash/btc_logstash.conf"
```
```
# setup and run Kibana on localhost
kibana
```

## Kibana
(Kibana is running on localhost for this project.)
1. Create index pattern
2. Create visualizations

## Results
![Alt text](results/032013-032019.jpg?raw=true "Weekly 03102013-03102019")
