EXERCISE 5
==========

version: '3.6'
services:
  elasticsearch:
    image: docker.elastic.co/elasticsearch/elasticsearch:7.9.3
    container_name: elasticsearch
    environment:
      - discovery.type=single-node
    networks:
      - elastic
    ports:
      - 9200:9200
      - 9300:9300

  kibana:
    image: docker.elastic.co/kibana/kibana:7.9.3
    container_name: kibana
    networks:
      - elastic
    environment:
      ELASTICSEARCH_HOST: elasticsearch
      ELASTICSEARCH_PORT: 9200
    ports:
      - 5601:5601

networks:
  elastic:
    driver: bridge