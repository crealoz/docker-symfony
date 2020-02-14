# docker-symfony

## Installation

This repository is meant to be kept as base for symfony project. Therefore, before using it, you need to create an empty
repository that will contain the new project. Once done, you can clone this repository, copy it to a location that points
to the new repository and begin to install.

This project needs docker on the system to be ran. 

- modify the .env to fit your need 
- run docker-compose build
- amend composer.json if needed
- run composer install in the folder htdocs
- run docker-compose up

You're done !

## Troubleshooting

**Nginx cannot start**

Check that system is not yet using the port used by the container.