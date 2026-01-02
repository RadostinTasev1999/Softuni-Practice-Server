## Server Deployment:
 1. Register to Google Cloud Platform [X]
 2. Create Project in GCP `Softuni-Practice-Server` [X]
 3. Install Docker [X]
 4. Create Docker image
    - Create Docker File [X]
    - Create Docker image [X]
    - Start local container `docker run -p 8080:8080 softuni-practice-server`

 5. Enable Artifact Registry
    - create a Repository [X]
    - change Docker image name `docker tag <CurrentImageName> <NewImageName>` [X]
    
    `europe-west4-docker.pkg.dev/softuni-practice-server/softuni`

6. Install GCloud SDK:

 - `gcloud init` - initialize the GCloud CLI [X]
 - `gcloud login` - login to GCloud
 - set current project `gcloud config set project PROJECT_ID`
 - check current project `gcloud config get-value project`
 - authorize GCloud to use Docker locally `gcloud auth configure-docker ` [X]

 `europe-west4-docker.pkg.dev/softuni-practice-server/softuni/softuni-server`

 - push docker image to Artifact Registry repository `docker push <ImageName>` [X]

 - deploy to CloudRun:
 `gcloud run deploy <ServiceName> --image <ImageName> --min-instances 0 --max-instances 1 --region europe-west4 --platform=managed --allow-unauthenticated` [X]

 Service URL: `https://practice-server-377820380014.europe-west4.run.app`




