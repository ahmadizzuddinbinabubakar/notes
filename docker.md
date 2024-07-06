# DOCKER
## Dockerise a repository
1. Create a docker file <br>
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
2. Build image <br>
  > docker build . -t this_is_a_tag
3. After finished build, the image can be ran in Docker desktop app <br>
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
