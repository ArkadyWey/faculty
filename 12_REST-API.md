# REST API 
- API : Application Programming Interface -- the interface between two computers.
- REST : Representational State Transfer -- one standard of communication method for the API (the language they speaka).

## REST 
- A way for two computers (client and server) to talk to each other. 
- The client sends a request and the server returns a response
- There are other options but this is the most common.
- This is implemented by using a set of rules to build web APIs.

- The rules are :
    1. Uniform interface : 
    2. Client-Server : 
    3. Stateles : Two parties don't store any info about each other.
    4. Cacheable : 
    5. Layered system : 
    6. Code on demand : 

### Resources 
- Organises resources (e.g. types data on the server) into a set of unique URIs (uniform resource identification) located at endpoints.
- URIs are called by nouns not verbs.

### Requests 
- A client interacts with a resource by making a request to he server with the endpoint for the resource over HTTP. 
- In a request, the URI is preceded by a HTTP verb which tells the server what the client wants to do with the resource.

- There verbs are : 
    1. Post : Create new resource (CREATE)
    2. Get : Read data about existnig resource (READ)
    3. Put : Update existing resource (UPDATE)
    4. Delete : Delete an existing resource (DELETE)

- These are achonymned with CRUD - create, read, update, delete.
- Request may also contain data in a json.

### Responses
- Contains HTTP status code. 
- Status codes are : 
    1. 200s - Successful request. 
    2. 400s - Error with request e.g. syntax.
    3. 500s - Error on server e.g. couldn't access the server.

- Response may also contain data also formatted as a dictionary. 