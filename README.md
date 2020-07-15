# docker-visits
Simple JS project that counts number of visits of the page. Accent on Docker files in order to build it containerised.

# Dockerfile
Simply takes node:alpine as base image (cause it has node installed, what is needed for the project).
Copies package.json to container and installs dependencies.
Then copies everything else from the project to container and run 'npm start'.

# docker-compose.yml
Simplifies running containerised project without long command line commands and allows to enable simple networking between two containers.
First container is redis which holds number of page visits.
Second is actual node application which counts how many visits were done on that page.
Also, maps host maching 4088 port to container port 8088 and restarts only on failure.
