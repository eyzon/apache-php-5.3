# Apache + PHP 5.3
This docker image contains apache and old PHP 5.3 for supporting older projects which need to run in Azure Web App environment.

## Docker Images for App Service Linux 
This repository contains docker images that are used for App Service Linux. 

## Components
This docker image currently contains the following components:

1. Apache (2.4.10) 
2. PHP (5.3.29)

## How to Deploy to Azure 
1. Create a Web App for Containers 
2. Update App Setting ```WEBSITES_ENABLE_APP_SERVICE_STORAGE``` = true 
>If the ```WEBSITES_ENABLE_APP_SERVICE_STORAGE``` setting is false, the /home/ directory will not be shared across scale instances, and files that are written there will not be persisted across restarts.
3. Go to container settings and change the image to **convergine/apache-php-5.3:latest**
Click save and then restart your web app. Will take few minutes to build it.

## Original Attribution
This docker image was built based on Azure-App-Service/php/5.6.40-apache image (https://github.com/Azure-App-Service/php/tree/master/5.6.40-apache). 
The image was built to support some of our clients who are not ready to migrate the code to latest PHP version and require PHP 5.3 environment.