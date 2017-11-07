# MongoDB manual for macOS X. 
### MongoDB manual installation an running .

Installation Overview
There are two primary ways to install MongoDB on a Mac. 
The best way to install MongoDB is with Homebrew. The other way to install MongoDB is by downloading it from the the MongoDB website.

Install and Run MongoDB with Homebrew
Open the Terminal app and type 

>brew update 

After updating Homebrew 

>brew install mongodb

After downloading Mongo, create the “db” directory.
This is where the Mongo data files will live. You can create the directory in the default location by running 
 
 >sudo mkdir -p /data/db

Or when running use different location of database:
>mongod --dbpath /usr/local/mongodb-data


Make sure that the /data/db directory has the right permissions by running

> sudo chown -R /data/db

Enter your password

Run the Mongo daemon, in one of your terminal windows run 

>mongod

>mongod --rest #run deamon with web interface on http://localhost:28017

This should start the Mongo server.

Run the Mongo shell, with the Mongo daemon running in one terminal, type 

>mongo 

in another terminal window. This will run the Mongo shell which is an application to access data in MongoDB.
To exit the Mongo shell run 

>quit()

To stop the Mongo daemon hit ctrl-c
