# Some inspiration from
https://training.play-with-docker.com/beginner-linux/

# Dockerfile commands
https://docs.docker.com/engine/reference/builder/

# List all docker images
docker images 

# view running dockers
docker ps --format "table {{.ID}}\t{{.Names}}\t{{.Status}}"
docker ps --format "table {{.ID}}\t{{.Ports}}\t{{.Names}}\t{{.Status}}"
https://docs.docker.com/engine/reference/commandline/ps/


# Stop all running Docker containers
docker kill $(docker ps -q)

# Delete all containers not running
docker system prune

# Attach VSCode to running container
https://code.visualstudio.com/docs/remote/attach-container

# Docker compose
docker-compose --profile airflow up
docker-compose --profile airflow down

docker-compose --profile superset up
docker-compose --profile superset down

# Three steps up Airflow
- curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.3.3/docker-compose.yaml'
- echo -e "AIRFLOW_UID=$(id -u)" > .env
docker-compose up
docker-compose --profile airflow up
docker-compose --profile superset up


# 99 Airflow 
mkdir 99-airflow
cd  99-airflow
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.3.2/docker-compose.yaml'
mkdir -p ./dags ./logs ./plugins
echo -e "AIRFLOW_UID=$(id -u)" > .env
docker-compose up airflow-init #initialize
docker-compose up
