Hi there !

Hope you'll enjoy playing with this application. 
The only requirement for you is to have a web server running. Put the application into your web server repository and launch it.
This application was developped using the built-in NodeJS web server.
Please note that blocked streets keep this status on reload if the user forget to unblock the street. Do not hesitate to use the "Unblock all the streets" button to make sure that the routing returns the default coordinates.

A few bugs might still be present, but nothing to ruin the whole user experience :)
I've noticed 2 bugs which could be fixed later :
- Sometimes, taxis are randomly popping on the map and they are running reaaaally slowly. I guess this happen when one trip is missing (for example when every streets which lead to an ending point are blocked).
- The routing service can provide coordinates located slightly outside Dresden and the application can't handle such data. The way I "fixed" it is by ignoring the file and loading the next one.

Don't worry about the "Cannot read property "split" of null error". It's probably because the refresh rate of the trail is really high (every 10 ms). So it tries to iterate on a path not being rendered (it's my opinion, maybe it's something else). Either way, you can leave it like this (except if you don't like red lines to appear in your console).

One way to fix many small bugs should be to track every path with its data from the CSV. Because very path (even when finished) is still present on the document. So when the user blocks a specific streets, the loop which retrieves the data from the CSV file give the right properties to the right path. For example, the first path is finished and is being deleted. The user blocks a street so the loop is iterating through the CSV file. The 1st line of the CSV will be linked with ... the first path in the document (so here, the 2nd trip because the first one is no more present on the document). So the solution should be something like : When a path is finished, delete it from the document AND from the array containing the CSV Data. 

When you want to load a specific file (file n°22 for the Long Night Of Science), do not forget to change the timestamp variables (time variable and incrementedTimeStamp variable) with the first date of the file you want to load and obviously the fileIterator variable (1 to load the first file, 2 for the second ...). Trips are within the Data folder

This application can be improved in a hundreds,thousands of way so do not hesitate to take a look at the code !

Have fun !

Project ExCELL team