## If the docker containers have already been created, but are stopped run this commands

`docker start kafka pyspark`

# First Time Loading Containers

## Create the network bridge in order for the jupyter notebook to connect to kafka
 
`docker network create my_bridge`

## Start the kafka server

`docker run -d --net my_bridge -p 2181:2181 -p 9092:9092 --env ADVERTISED_HOST=kafka --env ADVERTISED_PORT=9092 --name kafka spotify/kafka`

## Build the dockerfile

`docker build -t pyspark-local pyspark/`

## Start the pre-configured pyspark juypter notebook 
 
`docker run --net my_bridge --name pyspark -p 8888:8888 pyspark-local`
 
## Open up http://localhost:8888 (Jupyter Notebook with pyspark)

## Open the Simple Kafka Consumer and Producer

## Change the API and Token Keys in the config.py file

## Open the Twitter Kafka Consumer and Producer
