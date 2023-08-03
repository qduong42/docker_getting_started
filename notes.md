commands:

- docker built -t name dir
    - -t builds image
	- eg: docker built -t getting-started .

- docker run -dp 3000:3000 getting-started
  - docker run -dp x:y name
	- -d = detached -p = create mapping betwwen host port x to containers port y

- docker ps => list containers

- docker stop containerid
  - docker rm containerid

- docker image ls

- docker login -u qduong42

-docker exec <container-id> cat /data.txt

- PERSIST DATA COMMANDS:
  - docker volume create name

  - docker run -dp x:y --mount type=volume,src=VOLUME_NAME,target=DIR_TO_TARGET_DB NAME

- BIND MOUNTS
  - docker run -it --mount type=bind,src="$(pwd)",target=/src ubuntu bash

- Stop interactive container session
  - Ctrl + D

- run app in development container
  - docker run -dp 3000:3000 \
    -w /app --mount type=bind,src="$(pwd)",target=/app \
    node:18-alpine \
    sh -c "yarn install && yarn run dev"
  - -w sets working directory 

- dog logs container-id