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
___
* React
  * JS library for building UIs
  * Components - small and isolated pieces of code
    * tell React what we want to see on the screen
    * when data changes, React efficiently updates and re-renders component
    * React.Component classes
    * Components take in parameters or 'props' and returns a React Element, or hierarchy of views, to display through the render () method - syntax is jsx, not html - jsx comes with full power of js
      * e.g. ShoppingList extends React.Component > {this.props.name}
    * instead of class we have className


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
* /public/index.html - remove comments and change title
* /src/index.js - remove comments and service worker
* /src/App.js - npm start to load on localhost 3000
  * remove everything between the <div> tags, change className to "container"
* npm install bootstrap css framework to make styling easier, import it into App.js
* npm install react-router-dom - makes it easier to route urls to components
* create router element - helps us manage specific url paths to different components that will help us load on the page - put all that we want to route in <Router> element
* import into App.js the components we'll create
* create each of the following components in separate files in components folder in src directory:
  * Navbar
  * '/' ExercisesList
  * '/edit/:id' EditExercise
  * '/create' CreateExercise
  * '/user' CreateUser
* add basic component stub info into each component to test connections are working:
```
import React, { Component } from 'react';

export default class ExercisesList extends Component {
  render() {
    return (
      <div>
        <p>You are on the Exercises List component!</p>
      </div>
    )
  }
}
```
* add div className 'container' to App.js to give some space on navbar left and right
* build out each component by:
  * adding constructors before render () method for each class
  * set this.state
  * create methods for each class - using this.setState() and e.target.value - this refers to the whole class - use binding for this
  * hard code simple data and create form to test - componentDidMount()
  * this.state.users.map takes data from DB and maps over it and displays it
  * use npm install react-datepicker for date picker package - import it along with styling for datepicker
  * connect front-end with back-end
    * do this by getting front end to make http requests to the server endpoint on the backend - use the axios library to do this - npm install axios - and import into components

