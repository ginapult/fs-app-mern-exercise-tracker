# fs-app-mern-exercise-tracker

## MERN
* MongoDB - document-based open source DB
* Express - web app framework for Node.js - lightweight and fast
* React - JS front-end library for UI
* Node.js - JS run-time env that executes JS outside a browser (server)
___
* Mongoose - schema-based solution to model app data (easier to use MongoDB in Node.js)
* CORS - cross origin resource sharing - allows AJAX request to access remote hosts - access stuff outside server from our server
* dotenv - loads env variables from dotenv file
* nodemon - global - npm install -g nodemon

### MongoDB
* table = collections
* rows = documents
* join = $lookup
* foreign key = reference
* documents BSON format - binary JSON
* subdocuments - can nest inside eachother - data accessed together stored together
* MongoDB atlas - easy way to use MongoDB
* MongoDB ObjectId - unique across collection - we'll let MongoDB handle this
* Mongoose .find() - returns a promise, json format

## Steps

### Back-end Start
* MongoDB
  * Create new MongoDB Atlas Project & Cluster
  * Whitelist IP address
  * Create DB user

### Front-end Start
* React
  * use npx-create-react-app to set up front-end

### Back-end Complete
* Connect MongoDB and Google cloud
  * create backend folder
  * npm init -y
  * npm i express cors mongoose dotenv
  * npm i -g nodemon (if not already installed)
  * create server.js in backend folder
  * connect server to MongoDB Atlas - use dotenv to store - get connection string from MongoDB Atlas

* Create mongoose models and routes, import models to routes, and routes to server.js
  * create models folder and create user and exercise model files
  * create routes folder for API endpoint routes so server can perform CRUD operations
  * import routes into server file - require the files, then app.use the files
    * server.js - establishes:
      * '/users'
      * '/exercises'
    * routes/users.js - establishes:
      * '/' get
      * '/add' post
    * routes/exercises.js - establishes:
      * '/' get
      * '/add' post
      * '/:id' get
      * '/:id' delete
      * '/update/:id' post

* Test the API using Insomnia or Postman  
  * post request to add a user - 'http://localhost:5000/users/add' - use body > json > get "User added!"
  * get request to get the users back - 'http://localhost:5000/users/'
  * go see the new users on the MongoDB dashboard
  * do the same post and get for exercises
  * finish exercise routes with update and delete

### Front-end Complete




