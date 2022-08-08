# build the image based on python:latest image
FROM python:3.7-slim-buster

# the work directory inside the container
WORKDIR /

# copy the requirements file inside the container
COPY ./requirements.txt /requirements.txt

RUN apt-get update

RUN pip3 install --upgrade pip

RUN apt-get install -y gcc
RUN apt-get install -y python3-dev graphviz libgraphviz-dev pkg-config

# install the requirements using pip3
RUN pip3 install -r requirements.txt

RUN mkdir app
WORKDIR /app

# copy the project artefects into the container under the root directory
COPY . .

RUN chmod +x entrypoint.sh

ENTRYPOINT [ "./entrypoint.sh" ]