# GoogleSpringAppEngine

This project is the example of Spring boot application deployement on app engine.This project use app engine flexible.We created docker images using command (docker image build -t <IMANGE_NAME> .)) and before that please run (./gradlew clean eclipse bootRepackage) Since this command create jar file in lib folder which will be used in docker file to create docker image.
We have added depenedancies of app engine and app.yaml to make application deployable on GCP.
In app.yaml(runtime: custom) define docker images application.
docker image should be in convention of GCP like <docker image build -t <region>/<project-id>/<imagesname>:<version> .)

after image is created successfully ,run (gcloud app deploy)
This comand will deploy image to docker container of GCP and then deploy it on app engine with default as service name in app engine.
By default ,your application should be run on port 8080 since appengine map this port to NginX.If you use different it give 502(BAD GATEWAY)
You can stop service in GCP app engine dashboard.

You can check logs in stackdriver,Link of stackdriver is in app engine dashboard(version).
There are more configuration you can provide in app.yaml.
Most important : app.yaml and DockerFile should in same folder . like this appllcation has.
To run this application ,Please provide key.json in String format in application-default.ymlof credential field.


