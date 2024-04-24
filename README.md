# Devspoon-Projects

This is a repository introducing open source managed by devspoon.

# django project

## devspoons-portfolio-blog

This project supports the development of personal homepages such as portfolios and blogs. Based on Django, it provides advanced technologies such as Class View, Modelform, and Admin Custom. It leverages a variety of external libraries that are actually used. It use redis and celery. This project includes most of the functionality required for Django commercial services.

- github repository : [devspoon-portfolio-blog]

### Features

- **Separated config(settings) file management** : Setting files are separated with base(common file), dev, prod, stage, test. So user can choice a condition for any server status of development.
- **Separated file management** : Normally Django provides views.py, admin.py and models.py respectively. However, it is very difficult to manage all classes and functions in one file. So this project has separated file management to show how it can be handled.
- **Replication database management** : In a distributed system, databases are created in a replicated state. So django needs a connection point for reading and writing. This project shows you how to use replica_router.py to handle cases.
- **test** : Based on pytest, using faker and factory boy. support nose
- **profiling** : Support silk
- **Github action test** : Push to github and the github action Django CD with Testing version to OCI” will run automatically.
- **github action distribute** : Push to github, go to "Django CD with staging version to OCI" in the action menu, and click "run workflow" to start deployment.
- **Redis cash** : Supports cache, session, and celery worker buffers. Most view classes use the Redis cache, and admin.py also handles when content is deleted or updated.
- **Celery** : During the account creation process, account information that is not confirmed by email for a certain period of time will be deleted.
- **Docker** : Using the [devspoon-web] repository. This includes nginx, unicorn, mysql, redis, monitoring, etc.
- **Monitoring** : Support sentry
- **email configuration** : mailgun, sendgrid, sendinblue
- **Social Account** : google, kakao, naver
- **Package management** : Using poetry

# Infrastructure integration solution for startups

**devspoon** Open sources are an integrated web, API development, and project management solution for startups and small development teams. For all projects, you can install only the items you want or install all services at once through docker and docker-compose.

## devspoon-web

This open source project offer docker that three kind of web or API service solutions by php, gunicorn, uwsgi based on nginx server.
You can easily create custom configuration files for nginx using a shell script.
Supports https and certbot auto-extension script.
there are default security settings in the nginx config file.
docker-compose allows you to easily install and operate multiple domain servers on one server.
For server caches, docker-compose supports installing and connecting redis and redis-state.
Anyone can install web services easily using docker and docker-compose.
Af you want to use python and php service at same time, this solution can help you better.

- github repository : [devspoon-web]

### Features

- **Support to make configuration files for each service(conf, certbot)** : You can use a shell script to generate conf files for https and proxy settings in nginx. Supports a script to restart docker using crontab to complete certbot authentication of the docker container.

- **Efficiently dockerfile configuration for development and service operation** : The log folder is interlocked by "volumes" in docker-compose.yml so that user can can be tracked problems even when the docker container is stopped. Webroot, nginx config, etc. are frequently modified during development so these are interlocked by "volumes"

- **Provide reverse proxy function** : Multiple web and app services can be provided through one nginx with php or python and services can be provided simultaneously. A shell script is provided to easily create a proxy config file so that it can be integrated with the web UI of other services.

- **Provides easy distributed service operation method** : You can use multiple web servers through proxy, and you can use multiple app servers on one web server.

- **Easy service changes using Docker-compose** : In docker-compose, various configuration items are defined and commented out. By deleting comments or adjusting your desired settings, you can easily create an environment that suits your purposes.

- **log file collection** : Log files for all services are stored in log/<service> and can be monitored even after container termination.

- **redis and ssl** : Information such as configuration files, data, and keys for Redis and SSL are attached as volumes to the redis and ssl folders in docker-compose, so they can be reused when the container is terminated and restarted.

## devspoon-startup-web

devspoon-startup-web is an integrated management solution that allows you to easily build the solutions needed for startups (openproject, jenkins, gitolite [private git server], Harbor [private Docker server]).
A single docker-compose can be used to install various development, backup, and management services singly, in groups, or collectively.
This repository is based on the [devspoon-web] project. devspoon-web is an open source that allows you to easily build a web or API based on php, python, django, nginx, and redis using docker-compose.

- github repository : [devspoon-startup-web]

## Project management solutions

- **[OpenProject]** : Open source project management software to help you work on your project efficiently

  - Work assignment and issue tracking features allow you to manage projects and personnel easily and intuitively.

- **[Jenkins]** : As one of the CI tools, CI (Continuous Integration) refers to continuous integration, which is an automated process for developers, and new code changes are automatically built and tested regularly to notify developers to solve problems that can occur when multiple developers develop simultaneously. Software that helps secure development stability and reliability

  - Development automation (CI: Continuous Integration) can be configured directly and CD (Continuous Delivery/Deployment) can be linked.

- **[Gitolite]** : Configuration Management Tool. user can install git server software at own server

  - Gitolite is linked with openproject and jenkins, and can be used efficiently without repository public and limitations on the capacity restriction of git server and public storage.

- **[Harbor]** : The Private Docker Registry Server for businesses that store and distribute Docker Images

  - Using the harbor, you can build an independent docker image according to the type, version, and kernel environment type of the smart TV, IoT development board, and download and install the docker image to any new server at any time from the docker hub.

## devspoon-startup-tizen

devspoon-startup-tizen is an open source solution that can easily build a reliable Tizen development environment using Docker.

- github repository : [devspoon-startup-tizen]

## Features

- **Support to make configuration files for each service(conf, yml etc)** : Using shell script, you can easily make and manage the configuration files required for nginx, php, dockerfile, etc. with only the information required by the user's keyboard.

- **Efficiently dockerfile configuration for development and service operation** : The log folder is interlocked by "volumes" in docker-compose.yml so that user can can be tracked problems even when the docker container is stopped. Webroot, nginx config, etc. are frequently modified during development so these are interlocked by "volumes"

- **Provide reverse proxy function** : Through a single nginx, you can provide multiple web and app services using PHP and Python, as well as project management services at the same time. Provides a shell script to easily create proxy configuration files for integration with the web UI of other services.

- **Building a Tizen-based IoT development environment** : devspoon-startup-tizen can easily build the complex configuration required to develop Samsung Tizen-based IoT devices using the already verified Dockerfile and Docker-compose.

## Community

- **Website** : Owner's personal website is [devspoon.com](devspoon.com)

## Partners and Users

- Lim Do-Hyun Owner Developer/project Manager, bluebamus@gmail.com

<!-- Markdown link-->

[devspoon.com]: devspoon.com
[devspoon-portfolio-blog]: https://github.com/devspoon/devspoon-portfolio-blog
[devspoon-web]: https://github.com/devspoons/devspoon-web
[devspoon-startup-web]: https://github.com/devspoons/devspoon-startup-web
[devspoon-startup-tizen]: https://github.com/devspoons/devspoon-startup-tizen
