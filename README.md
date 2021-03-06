an example of how to create a rest endpoint using Python and Flask.

This service calls a local sqlite database. Please see databases directory for more details. 

This projet was written using PyCharm Community Edition.   

Project Database
-----
This project uses a local sqlite for a repository.  


Swagger
-----
This project contains a swagger ui.  

[For more information regarding swagger. Click here.](https://swagger.io/)

[For more information regarding connexion. Click here.](https://connexion.readthedocs.io/en/latest/)

To view this api's swagger ui, run this application, then navigate to [http://localhost:5000/ui/]

You can test out this api entirely from the swagger ui page. 

This app is also deployed using [heroku](https://www.heroku.com/).  To view deployed api swagger navigate to [https://sdet-flask-api.herokuapp.com/ui/]


Rest Api 
-----

#### Users Api

GET - getAll: [users/v1](http://localhost:5000/users/v1)

GET - getByUsername: [users/v1/darth](http://localhost:5000/users/v1/darth)

PUT - updateUserEmail: [users/v1/darth](http://localhost:5000/users/v1/darth) + include a json body with new email.

DELETE - deleteUsername: [users/v1/darth](http://localhost:5000/users/v1/darth)

#### Users Api - deployed on heroku

GET - getAll: [users/v1](https://sdet-flask-api.herokuapp.com/users/v1)

GET - getByUsername: [users/v1/darth](https://sdet-flask-api.herokuapp.com/users/v1/darth)

PUT - updateUserEmail: [users/v1/darth](https://sdet-flask-api.herokuapp.comusers/v1/darth) + include a json body with new email.

DELETE - deleteUsername: [users/v1/darth](https://sdet-flask-api.herokuapp.com/users/v1/darth)


#### Locations Api

GET - getAll: [locations/v1](http://localhost:5000/locations/v1)

GET - getByState: [locations/v1/ca](http://localhost:5000/locations/v1/ca)

PUT - updateCapital: [locations/v1/ca](http://localhost:5000/locations/v1/ca) + include a json body with new capital.

DELETE - deleteLocation: [locations/v1/ca](http://localhost:5000/locations/v1/ca)

#### Locations Api - deployed on heroku

GET - getAll: [locations/v1](https://sdet-flask-api.herokuapp.com/locations/v1)

GET - getByState: [locations/v1/ca](https://sdet-flask-api.herokuapp.com/locations/v1/ca)

PUT - updateCapital: [locations/v1/ca](https://sdet-flask-api.herokuapp.com/locations/v1/ca) + include a json body with new capital.

DELETE - deleteLocation: [locations/v1/ca](https://sdet-flask-api.herokuapp.com/locations/v1/ca)


TDD - Integration Tests
-----
This api is fully tested with Unit Tests and Integration tests.  Please see tests directory for examples.

Tests connect to test.db for integration tests.

    
Flask Project
-----
This project is a Flask project. [For more information click here](http://flask.pocoo.org/)
    
    
Docker
-----
This application can be run in Docker.  Please see Dockerfile for image setup.  Steps to create an image & how to run 
the app in a container list below. (must have docker installed)

Create a docker image: `docker build -t flask-api .`

Run docker container: `docker run -it -p 5000:5000 flask-api`

__*** Once app has started, view the swagger ui by navigating to [http://localhost:5000/ui/] ***__

View docker images: `docker images`

View docker containers: `docker ps -a`

Remove docker images: `docker rmi $(docker images -q)`

Remove docker containers: `docker rm $(docker ps -aq)`

[Click here for more information regarding docker](https://docs.docker.com/)


__* Note: this flask app by default runs as a development server, not meant for production. Docker & gunicorn 
is used to productionize this app.  This docker container runs as as a production WSGI server, with 4 workers 
via [gunicorn](https://gunicorn.org/). *__

   
Continuous Integration(CI)
------------
A web hook has been setup with Travis CI for all Push and Pull Requests.

A web hook has also been setup with Github Actions for all Push and Pull Requests.
 

Continuous Deployment(CD)
------------
This app is setup to deploy via [heroku](https://www.heroku.com/) after a successful CI.  

To view deployed api swagger [click here](https://sdet-flask-api.herokuapp.com/ui/)
