# Back-end

## About

The Back-end Folder contains:
  - App.js and Index.js: The main files to start the app and the server and connect to the database (Database must have been created first)
  - Routes: Based on the requests, the routes will call the controllers ( and if needed, the middlewares) 
  - Middlewares: 
    - Authentication
    - Authorization
    - Functions used by the controllers 
  - Controllers: Handle the requests and responses
  - Utils/Database Implementation
    - Database code (.sql)
      - The database contains the tables and the admin user
    - .js files to import data 

More info:
  - Authorization: Every user is stored in the database with a role ("admin", "simple_user")
  - Authentication / JWEB Token: 
    - The user logs in and receives a WEB token
    - The token is used to authenticate the user in the requests
    - The middleware takes the token from the request header and checks if it is valid
  - Security : (DDOS Attacks (if implemented) )
  

### NodeJS Packages:
```json
  "name": "back-end",
  "version": "1.0.0",
  "description": "New npm folder",
  "main": "index.js",
  "scripts": {
    "test": "cross-env NODE_ENV=test mocha ./test/*.test.js",
    "test_admin": "cross-env NODE_ENV=test mocha ./test/06_admin.test.js",
    "start": "nodemon index.js",
    "dev": "nodemon server"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/ntua/softeng23-33.git"
  },
  "keywords": [
    "softeng23-33",
    "nodejs"
  ],
  "author": "team33",
  "license": "ISC",
  "bugs": {
    "url": "https://github.com/ntua/softeng23-33/issues"
  },
  "homepage": "https://github.com/ntua/softeng23-33#readme",
  "dependencies": {
    "bcryptjs": "^2.4.3",
    "cookie-parser": "^1.4.6",
    "cors": "^2.8.5",
    "csv-parser": "^3.0.0",
    "dotenv": "^16.3.1",
    "express": "^4.18.2",
    "fast-csv": "^5.0.0",
    "isarray": "^2.0.5",
    "jsonwebtoken": "^9.0.2",
    "multer": "^1.4.5-lts.1",
    "mysql": "^2.18.1",
    "mysql2": "^3.9.0",
    "promise": "^8.3.0"
  },
  "devDependencies": {
    "chai": "^4.3.4",
    "chai-http": "^4.4.0",
    "cross-env": "^7.0.3",
    "mocha": "^10.2.0",
    "nodemon": "^3.0.3",
    "supertest": "^6.3.4"
  }
```


## Getting Started

### Initializing database
1. Start a MySQL Server (We used XAMPP)
    If you are using Linux and have LANMP installed, you can start the server with the following command
    ```sh
    ./run_lampp_linux.sh
    ```
2. Create the database using the ./utils/ntuaflix_create_schema.sql
   - a. In your DBMS use this file 
   - b. If you are using linux run the following command in the terminal
    ```sh
    ./create_schema_linux.sh
    ``` 
   - c. If you are using windows run the following command in the terminal
    ```sh
    ./create_schema_windows.sh
    ```
3. If you want to add the data from the tsv files to the database, you can use the following command
    ```sh
    cd ./utils/import_data
    node main_import.js
    ```

### Start the Back-end
Firstly the local web development toolkit (like XAMPP) must be running. 
1. Install all dependencies
   ```sh
   npm install 
   ```
2. Run the REST-API
   ```sh
   npm start 
   ```

## Testing
Firstly the local web development toolkit (like XAMPP) must be running. 
1. Install all dependencies
   ```sh
   npm install 
   ```
2. Test the REST-API
   ```sh
   npm test 
   ``
