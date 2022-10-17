# tiny_cv2.docker
Small size docker image that include opencv + python3 + ubuntu. It contains:
- opencv==4.6.0
- Python3.8 @ ubuntu 20.04
- pip installed opencv-python opencv-contrib-python
- Only 185MB in compressed size, 500MB in docker size

## Usage
```bash
docker pull diyer22/tiny_cv2:latest
```

Or, as base image:
```dockerfile
FROM diyer22/tiny_cv2:latest
RUN pip install -r requirements.txt
```

## Build from dockerfile
```bash
docker build -t diyer22/tiny_cv2 .
```
you can change the ubuntu version or opencv version in the Dockerfile
```Dockerfile
FROM ubuntu:20.04
# Note: Python version is the ubuntu's default python 
# For ubuntu:20.04, Python version is 3.8
ARG OPENCV_VERSION=4.6.0
```

## Others
Our dockerfile is modified from [dkimg/opencv](https://github.com/dkimg/opencv/blob/master/ubuntu/Dockerfile) with those differences:
- No more repeated installation of opencv-python or opencv-contrib-python
- More popular and mature Python version

