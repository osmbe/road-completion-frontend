# Road-completion

The road-completion tool allows users to: 
- Authenticate using OSM
- Set the status of an issue (fixed, false-positive, too difficult)
- Add notes to an issue
- View their fixed issues

## Backend
The backend API is build using the following technologies:
- [Nodejs](https://nodejs.org/en/)
- [MongoDB](https://www.mongodb.com)


For running the backend you have 2 choices:

### Docker
Make sure [docker-compose](https://docs.docker.com/compose/) is installed before running the following commands:

Before running the script, make sure other instances of the backend container are stopt:
```
# navigate to the backend folder
cd backend

# stop all running docker-compose containers
docker-compose stop
```

```
# navigate to the backend folder
cd backend

# the run script builds and runs the docker container
sudo sh run.sh
```

The REST API is now running on port 3000


### Node
If you want to run the backend on your local machine make sure [nodejs](https://nodejs.org/en/) and [MongoDB](https://www.mongodb.com) are installed.

In the app.js file, change the mongodb url to: `mongoose.connect('mongodb://localhost:27017/osoc18road',{ useNewUrlParser: true });`

```
# navigate to the backend folder
cd backend

# install all node modules
npm install

# run the app.js file
node app.js
```

If everything is running correctly you should see something like:
```
App running on port 3000
Connected to mongodb server
```

The REST API is now running on port 3000

## Frontend

The backend API is build using the following technologies:
- [Nodejs](https://nodejs.org/en/)

For running the frontend you have 2 choices:

### Docker
Make sure [docker](https://www.docker.com) is installed before running the following commands:

Before running the script, make sure other instances of the frontend container are stopt:
```
# view running docker containers
docker ps

# copy the id from the docker container that contains the frontend
docker stop $id
```

```
# navigate to the backend folder
cd frontend

# the run script builds and runs the docker container
sudo sh run.sh
```

The frontend can now be accesed on port 8080


### Node
If you want to run the backend on your local machine make sure [nodejs](https://nodejs.org/en/) is installed.

In the js/main.js file, change the url at the top of the page to the link where the backend is running (probably http://localhost:3000/API/)

```
# navigate to the backend folder
cd backend

# install all node modules
npm install

# run the app.js file
npm start
```

The frontend can now be accesed on port 8080
