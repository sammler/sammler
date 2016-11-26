- Need a possibility to validate the data-model
	- programmatically - a must
	- downloading the empty app containing the data-model
	- selection tool (being exposed to a mashup)
	- data-model viewer?

- Missing one use case:
	- The push scenario

- In all use cases pivoting will be required in the long run

- Introduce conventions
	- LOAD * or NOT Load *

- Handling uploads to S3, etc. is not part of the problem-space, that can be shown with third party libraries (maybe included in Qliktive)	

# MVP

- Extensibility
- Push first  
(then we don't have to take care of connectivity in the short run)
	- Realized with an inline table	
- Local files (resp docker volumes in the context of QAP Core)
- We could start with `Load *`, but that is probably not enough for the MVP
- Share with Developer relations
- EarlyInsights exposure

# Action points
- Create the graphical overview how the Data Creation Library
- Find a name for it



#1 - Pull flat file from Cloud Provider

Comments:
- In case of QAP Core it's a docker volume (from an engine perspective that's basically just all about reading from the local file system)
- The docker volume could just mount an S3 volume
- Could cover all table-files / flat files

Questions: 
- Do we need somebody to help?
- We are talking about credentials / secure connnection string?

#2 - Load two Excel files (Data modeling)

- New problems can occurr: 
	- Synthetic keys
	- Data modelling can fail

- By introducing a convention (force classification of tables) we could solve the problem and reduce the scope	

#3 - Loading from publicly available REST service

- Authentication is interesting to solve
- Limit the possible structure of a REST service
- More complicated webservices could be handled by the push scenario

#4 - Excel with advanced data modeling (incl. pivoting)

- Pivoting is important
- Not MVP ;-)

#5 - Loading QVD files from S3


#6 - Combine different files from different cloud providers

- Not MVP
- Selling point of multi-source (!!)

#7 - Extensibility of the Data Creation Library (Connection)

- Key functionality from the beginning
- Must have, everything should be built on top of that capability

#8 - Extensibility of the Data Creation Library (Data Modeling)