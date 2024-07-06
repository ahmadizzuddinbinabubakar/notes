# DOCKER
## Dockerise a repository
1. Create <em>.dockerignore</em> file in root folder
2. Create <em>Dockerfile</em> in root folder <br>
- base image <br>
  > FROM python 3.10 <br>
- working directory <br>
  > WORKDIR /app <br>
- install dependencies <br>
  > COPY requirements.txt <br>
  RUN pip install --no-cache-dir -r requirements.txt <br>
- copy source code <br>
  > COPY . . <br>
- export a port <br>
  > EXPOSE 5100 <br>
- run the app <br>
  > CMD ["python", "app.py"] <br>
3. Build image <br>
  > docker build . -t this_is_a_tag
4. After finished build, the image can be ran in Docker desktop app <br>
<br>

## Deploy in Google Cloud Run
1. Prerequisites
  - created a Google Cloud account
  - installed gcloud CLI
2. Get the image on a registry.
  - on Google, use Artifact Registry.
  - create a repository for the docker image
  - store the image in a specific region
  - copy the region link and set as tag on the image
    > docker tag local-tag YOUR_REPO_URL
3. Upload into Google Cloud
    > docker push YOUR_REPO_URL
4. Deploy image
  - in Cloud Run, create service
  - select the container image
  - allow unaunthenticated invocations (to allow anyone to access)
  - set CPU is only allocated during request processing (to keep using at $0 but will cold start each trigger)
  - set allocated memory (if using AI will need more RAM)
  - decrease amount of autoscaling (if not commercial project ~3 is sufficient)
  - deploy
  - a URL for the webapp will be provided
5. To use in a different machine
    > docker pull

## Docker Compose
1. In root folder, create docker-compose.yml
  - version of Compose file
    > version: `3`
  - define all services (applications) that you want to run in one go
    > services:  <br>
    &emsp; app1-name: <br>
    &emsp; &emsp; ... <br>
    &emsp; app2-name: <br>
    &emsp; &emsp; ... <br>
    &emsp; app3-name: <br>
    &emsp; &emsp; ... <br>
  - defines the Docker image that will be the base of the container
    > image: "postgres:9.6-alpine"
  - similar to the image from the previous example, but instead of using already prepared Docker image, Compose needs to create one based on Dockerfile
    > build: ./sample-app
  - specifies the name of the outcome container
    > container_name: sample-postgres
  - map a port of your PC to the exposed port of the container
    > – 8080:8080
  - define environment variables that will be inside Docker container
    > environment: <br>
      – ENV_VAR_1: value1 <br>
      – ENV_VAR_2: value2 <br>
      – ENV_VAR_3: value3 <br>
  - additional settings may need to be added based on the type of application
2. Useful commands in development
  > docker-compose up -d --force-recreate <br>
    docker-compose down --rmi all
3. In root folder, start all instances
  > docker-compose up
4. To stop all instances
  > docker-compose down
