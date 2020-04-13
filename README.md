# Elastic stack

easy application performance monitoring with docker and elastic stack

### Requirements

1. [Docker](https://docs.docker.com/engine/installation/)
2. [Docker Compose](https://docs.docker.com/compose/install/)
3. Ensure that no processes are using the ports below:
    - `80` **(http)**
    - `5000` **(logstash)**
    - `5044` **(logstash)**
    - `5045` **(logstash)**
    - `5601` **(kibana)**
    - `8200` **(apm-server)**
    - `9200` **(elasticsearch)**
    - `9300` **(elasticsearch)**
    - `9600` **(logstash)**
    
4. Clone this project
    ```bash
    git clone https://github.com/JudeSeide/elastic-stack.git
    ```   

### Build the containers

***Tip**: you may omit the `--no-cache` if it's the first run*

```bash
docker-compose build --no-cache
docker-compose up -d
```

And you're done!

### Useful commands
```bash
docker-compose build --no-cache
docker-compose ps
docker-compose pull
docker-compose rm
docker-compose up -d --force-recreate
```

### Add index to elasticsearch

```
GET application-*/_ilm/explain

PUT _template/application
{
  "index_patterns": ["application-*"],                 
  "settings": {
    "index.lifecycle.name": "application",      
    "index.lifecycle.rollover_alias": "application"    
  }
}
```

