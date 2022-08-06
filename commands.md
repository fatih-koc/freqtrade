

## Docker Install
docker compose up -d


## Download Data 
'''
docker-compose run freqtrade download-data --exchange binance -t 15m

docker-compose run freqtrade download-data --timerange 20190101-20200101  --exchange binance -t 15m


## BAcktesting
'''
docker-compose run freqtrade backtesting --datadir user_data/data/binance --export trades  --stake-amount 100 -s MyStrategy -i 15m

docker-compose run freqtrade backtesting --timerange 20210101-20210520 --datadir user_data/data/binance --export trades  --stake-amount 100 -s TDSequentialStrategy -i 15m


docker-compose run freqtrade backtesting --datadir user_data/data/binance --export trades  --stake-amount 100 -s TDSequentialStrategy -i 15m



## Plot Chart
docker-compose run freqtrade plot-dataframe --strategy MyStrategy -p BNB/BTC -i 15m


## Hyperopt Create
docker compose run freqtrade new-hyperopt --hyperopt TDSequentialStrategyHyperopt

docker compose run freqtrade new-hyperopt --hyperopt TDSequentialStrategyHyperopt

## Hyperopt Train
docker compose run freqtrade hyperopt --hyperopt MyStrategyHyperopt --hyperopt-loss  SharpeHyperOptLoss --strategy MyStrategy -i 15m  

docker compose run freqtrade hyperopt --hyperopt TDSequentialStrategyHyperopt --timerange 20210101-20210520  --hyperopt-loss  SharpeHyperOptLoss --strategy TDSequentialStrategy -i 15m  




##### DOCKER

run up 
docker compose up -d

List all containers (only IDs)
docker ps -aq

stop all containers:
docker kill $(docker ps -q)

remove all containers
docker rm $(docker ps -a -q)

remove all docker images
docker rmi $(docker images -q)