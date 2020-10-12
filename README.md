# Learning Elasticsearch
Notes on what elastic search is, how it works and how to use it.

### How to run it
1. Copy the docker-compose.yml file
2. Run docker-compose to bring up the three-node Elasticsearch cluster and Kibana:
`docker-compose up`
3. Submit a _cat/nodes request to see that the nodes are up and running: 
`curl -X GET "localhost:9200/_cat/nodes?v&pretty"`
4. To load sample data and interact with the cluster go to http://localhost:5601/app/home#/tutorial_directory/sampleData (here we use Sample eCommerce orders).
5. Access Kibana console to query data: http://localhost:5601/app/dev_tools#/console 
6. Tear down the containers and volumes by running `docker-compose down -v`

### Documentation
1. Running Elastisearch with docker: https://www.elastic.co/guide/en/elastic-stack-get-started/current/get-started-docker.html
2. Elasticsearch guide: https://www.elastic.co/guide/en/elasticsearch/guide/current/_talking_to_elasticsearch.html
