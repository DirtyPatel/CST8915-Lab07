## What are the main differences between a Docker image and a Docker container?
- Docker Image are lightweight, read-only package that has code, runtime,  libraries, dependencies and settings needed for the app.
- Docker Container - is what you get when you actually run that image, its the live, isolated environment where the app executes.
## Explain how Docker's layered architecture improves efficiency.
- Union File Systems is the foundation of Dockers layered design. Each image is made up of multiple read-only layers like base OS layer, dependency layer and app layer. 
 Reusability: layers are shared across containers which saves disk space. 
 Faster builds: when something changes, docker rebuilds only the modified layer instead of the whole image. 
 Portability: these layers can be reused across machines and that makes the deployment fast and consistent.

 Basically, instead of sending the whole package every time, docker just reuses the parts that didnt change, making it super efficient and speedy. 
## Why does each container get its own writable layer?
- The container components are shared and read-only on the host OS to keep them lightweight. When Docker runs a container, it add a writable layer on top so the container can store temporary data, logs, and changes without altering the original image.

1) So that each container can operate independently
2) No container affects another container
3) When the container stops, its temporary changes disappear

## What are the benefits of using Docker Compose over running containers individually?
- Instead of manually running each container, Docker compose lets you define all services in one YAML file and start them together with a single command. 
    Benefits: 
    1) Its convenient to run or stop the whole multiservice setup with docker-compose up/down
    2) Everyone run the same config making it consistent.
    3) Automatically connects containers so they can talk to each other. 
    4) Easily scale services by increasing container counts

    * Its like managing a team instead of telling each person what to do 1 by 1 and you give the group a single plan and everyone working in snyc. 