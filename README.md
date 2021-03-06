# mesen
https://mesen-dot-uiu-server.appspot-preview.com/

![image](https://cloud.githubusercontent.com/assets/116057/20457220/ab4bc510-aec9-11e6-9316-709ab6e57d91.png)

mesen uses Google Cloud Vision API to detect face landmarks.

```sh
export GOOGLE_APPLICATION_CREDENTIALS=credentials.json
python main.py
```

```sh
curl -sL -X POST localhost:8080 -F 'image=@data/uesaka.jpg' | imgcat
```

or use as cli:

```sh
python convert.py data/pastak.jpg > result.png
```

## Run app on docker
It uses docker to deploy to google app engine.

You can launch the docker environment by following commands:
```sh
docker build -t mesen .
docker run -p 8080:8080 mesen
```

and open `http:://$(docker-machine ip):8080`

## Deploy
It's running on a container with flexible enviroment in google app engine 

```sh
gcloud app deploy
```

