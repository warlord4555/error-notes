<h3>Operation articles.insertOne() buffering timed out after 10000ms</h3>

__Model.method()__ have a timeout. It is timing out probably because you’re not connecting to the server, but mongoose throws no errors.
So make sure your Mongo Connection key is valid and you handled your errors good enough.

after realizing that the problem was in connection, i made sure the connection wasen't established and got another error

<h3> const serverSelectionError = new ServerSelectionError();</h3>

> ongooseServerSelectionError: connect ECONNREFUSED ::1:27017 Etc. Etc.

so basically change 
 __MONGO_DB_CONNNECT_STRING='mongodb://localhost/dbName'__
 to
__MONGO_DB_CONNNECT_STRING='mongodb://127.0.0.1/dbName'__

yes, just change __localhost__ to __127.0.0.1__

<h3>Error [ERR_HTTP_HEADERS_SENT]: Cannot set headers after they are sent to the client</h3>

i was trying to send response in a loop, just rebuilt my function.
