# CouchDb Distributed Keypass Storage

This is a proof of concept of an idea for sharing secrets among different people. Every user has it's own username and public/private key pair. The public key is stored on the remote Couch Db while the private key is stored on the browser's internal permanent storage (ideally encrypted with a password).
Each time a new document is created, it will be encrtypted with each user's public key and saved into the _secrets_ database. All the users will then be able to see its content by decrypting the content with their respective private key.  

### Prerequisites
The application does not require any backend framework to work. It only consists of 3 static files: `index.html`, `app.js`, and `app.css`, and some external JS library. In order to reduce the dependency on external sources, the JS libraries are cached locally. Therefore they need to be prefech from their respective origins. This is done by just executing `make install`. Therefore the only requirements are the following:

 - make
 - a web server
 - a couchdb server with CORS disabled for the application server address

### Configuration
The couchdb server address as well as the name of the databases is currently hardcoded in `app.js`. Two databases are used: one for the users, and one for the secrets.

## References
 - [JS Encrypt](https://github.com/travist/jsencrypt) the JS library used for encrypting the documents;
 - [Pouchdb](https://pouchdb.com) the JS library used for the backend storage;
 - [Couchdb](http://couchdb.apache.org) the backend storage;
 - [JQuery](https://jquery.com);
 - [Bootstrap](https://getbootstrap.com).

## TODOs
The list is too long... 


