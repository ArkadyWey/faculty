# Day 6 

## APIs in ML 

### What is an API?
- Application prpogramming interface 
- Set of protocols that enable interfaces to speak to each other 
- Sits at the centre of request and response cycle 
- If we think of restaurant - customer is client, waiter is API, kitchen staff are API server.

### Types of APIs 
- Private : Connect different software components within a single organisation. 
- Public : Provide public accesss to company's data. 
- Partner APIs : Enable two or more companies to access each others' data - e.g. skyscanner 

### REpresentational State Transfer 
- REST is most popular API architecture. 
- There aare others, like SOAP GraphQL - second one is probably better. 

- Get - retreive something 
- Put - replace something 
- Delete - remove something 
- Post - Create new 
- Patch - update something

Constraints to be considered RESTful 
- Uniform interface : 
- Client/server architecture : client requests resources and server holds resources. These can be updated independently aside from teh API contract that ties the two together. 
- Stateless :  each request contains all info the server needs to process request and shouldn't rely on previous requests. 
- Cacheable : Every resposnse should be cacheable 
- Layered system : Application composed of multiple layers
- Code on demand : server can provide executable code 

### The good and the bad of REST 

Good 
- Independent : server and client independent 
- Flexible 
- Scabalble - Becauyse of separation of servr and client 
- Lightweight -

Bad 
- Consensus - consistency across all REST APIs id hard 
- Versioning - practice of creating multiple version of same API is hard.
- Authentication - 
- Security - Weak API keys  

### Machine learning models and APIs  
- CLient is me and I want to classify a picutre. Server is model. 

### Security  - Best practices 
- Use HTTPS
- Monitoring  
- Rate limits - stops client hammering an API which would prevent it being used by genuine usersl. Request frequency limiation 
- Role based access control - controls access to API resources according to role of user. E.g. read only 
- Validation - Confirming data that is sent to API follows format and constraints / doesn't include harmful calls 

### Authentication and authorisation 
- Auth is process of identifying user making API request 
- E.g. HTTP, API Key Authentication, JWT, OAuth 

HTTP Basic 
- Client requests protected resource 
- API requests username
- Client sends them 
- API returns requests item 

API keys
- API is responsible for validating key that client provides 
- API keys are not role based permission in the same way as a password 

JWT 
- JSON we taokens 
- Secure way of sharinfg json dat between parties 
- Data is encoded and then server desrialises  
- Offers authentication and authorisation 

OAuth 2
 - Robust but hard to manage  
  
### Versioninig 
-major-update(non-backward-compatible-features).backward-compatible-feature.bug-fix-or-patch 
- Prevents breaking API when update is rolled out
- Breakinig changes are those that affect the user 

### FastAPI 
- Framework for building APIs - one alternative is FLASK, which has been around for longer.
- Use pydantic, starlette, uvicorn.

## Evaluating model performance 
David Peinador Veiga 
Mustafa Çaglar 

### Why do we evaluate Machine Learning (ML) models?
It allows us to... 
- Compare models 
- Estimate performance  
- Monitor drift -- model performane degrades over time 

- Business -- more profit and less cost 
- Ethics -- model is unfair and that's deterimental to a particular group 
- Regulatory reasons - regs psecifying the accuracy that a model has for given use case  

### Statistical and operational evaluation metrics
- Client doesn't care about statistical metric 
- They care about operational metric 
- Our job is to translate between the two  

### Examples we'll look at 
- Regression -- Predict continuous variable 
- Classification -- PReddict categorical outcomess 

### CLassification 

#### Accruacy
- Accuracy not good metric when class imbalance 
- Use confusion matric instead 

- There are different metrics of accuracy 
- PErformance measures are often linear combinations of these metrics 
- This is a messy space and different fields call the metris different things. 
- The linear combination of metrics you choose is application specific e.g. you care about false negatives a lot in medicine 

- Look at ROC and PR curves 

### Regression metrics
- Root mean square 
- Mean absolute error 
- There are others  

### Evaluation strategies 
- Split data into -- train, test, validation, out of sample 

Cross validation 
- Change where you are donig the train test split of the data 
- Iteratively validate on different sets 

Practical considerations  


## 3. Communicating at the right level 
Dinan Alasad  

### Intro 
Goals for the day 
- IDentify important leavers 
- Determine how to convey best 
- Practice comms in an interview setting 

### Why is it important
- Survival 

### What makes a good communicator?
- Good at listening 
- Empathy 

### Empathy in communication 
- If you don't understand who the audience is, it's impossible to tailor what you're saying

- Whp is audience? 
- What are your main points?
- What do they want to hear?
- Wht do you want them to feel?
- How do they want to hear?

### Interviews

- Please think of a time when you developed a machine learning model?
- What has been the impact of a model that you have created?
- What is your favourite machine learning algorithm?
- What other algorithms do you like?
- Could you explain how that works to a 10 year old?
- Do you have much excperience with disirtibution of models?
- What is your favourite programming language? 
- What packages do you know that are relevant to machine learning?
- Could you please tell me about your research in 1 minute?
- Where would you like to be in 2 years?    

### Notes 
- Don't necessarily ask for clariity... say that there are options?


### Pyramid principle  

