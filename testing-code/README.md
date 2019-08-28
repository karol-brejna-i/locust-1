# contents
This directory contains the contents of Locust testing code (code ran against System Under Test) that is run on Locust.

Additionally, it contains a dockerfile definition for building docker container for locust.


### Building the image
It assumes the code will be encapsulated into a docker image with:

```
docker build -t grubykarol/ci-experiment -t grubykarol/ci-experiment:0.0.1 .
```



```
docker build --build-arg HTTP_PROXY=$http_proxy --build-arg HTTPS_PROXY=$https_proxy -t grubykarol/ci-experiment -t grubykarol/ci-experiment:0.0.1 .
```


### Running the image
```
docker run --rm --name standalone --hostname standalone -e ATTACKED_HOST=http://standalone:8089 -e "LOCUST_OPTS=--no-web" -p 8089:8089 -d grubykarol/ci-experiment:0.0.1
```