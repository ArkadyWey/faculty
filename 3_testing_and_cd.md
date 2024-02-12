# Testing and CICD 

## 1. Testing
Tutor - Dan Corvesor 

### Importance of Testing in MLE 
- Reduce risk of failure 
- Verifies requirement 
- Improves design - forced to think about structure in order to incorpoorate tests
- Prevents regressions - failures dued to changes in code
- Improves documentation - tests describe what's happening 

### Types of testing 
- Unit testing - testing units
- Integration testing - looking at how units interact 
- End to end - does it all work together?
- PErformance testing - is security high / speed high / reliability 
- Smoke testing - simple tests at the beginning 
- Acceptance testing - legal thing -- ensure software meeting requirements that you set out with the client 

### Unit tests
Benefits
- Catchers bugs early in development 
- Promotes modular design 
- Targeter testing 
- Lots of frameworks support this e.g. pytest 

Best practice 
- Write tests alongside code 
- Include positice and negative test cases 
- Target edge cases and invalid input 
- Test one scenario per test 
- Use CICD and fixtures/mocking 

### Integration testing 
Benefits 
- Identifies defects in interactions between components 
- Confirms that the architecture that we implemented was correct 

Bets practice 
- Leverage stubs snd drivers to isolate otehr parts of the system 
- Perform the tests incrementally 
- Test with valid and invalid data 
- Use integration tests in CICD

### End to end test 
Benefits
- Confidence in while ystem 
- May catch more complex issues 

Best practice 
- Map test to expected user workflows and requirements 

### Performance tests 
Types 
- Load testing - how do I deploy application when I can't test 10000 users
- Stress testing - Stability, what's the mx number of users?
- Scalability - difference container systems and how do tehy scale? Hoew quickly can this happen?
- Endurance - If the system runs for a long time does that affect perforamnce? Am I going to run out of memory? KMaybe the system is caching and it runs out? 
- Security testing - external company test whether they can break the system 

### Smoke tests 
Right at the beginning 

### Acceptance tests 
Coupled with promises that you made to the client 

### Testing in MLE 
- Unit testing of models 
- Tesing ML pipelines 
- Testing API endpoints 
- Testing ML systems 
- Acceptance testing in ML systems 
- Testing ML data 

### Challenges 
- LAck of deterministic output 
- ML training is often continuous 
- PErformance metrics are not always accurate 
- FAirnbess ans bias are important but hard to test 
- Expensive load testing 
- Lots of interactions between systems

### Testing frameworks 
- JUnit 
- pytest 
- Se 
- jest 
- postman 

### Pytest 
Pytest is good 
- Autoamtic test discovery 
- TEsting error raising 
- More powerful assesrtions -- function that calls another function calls a specific number of parametersand what these parameters are
- Fixtures -- e.g. want to set up a database and test it / create some fake data - way that you separate logic to set up test and the test itself. This keep scode clean. 
- Parametrised test -- instead of having multiple tests you have one test that takes in multiple functions. 

### Writing testable code  
You should write code to make it easier to test 
- Modular design - one function, ine responsibility 
- Loose coupling 
- Separation of concerns 
- Remove hidden states 
- Well defined interfaces 

### Test-driven development 
Write the t3st before the code 
- Write the test you expecrt to get 
- Update function until it satisfies the test 


## 2. CICD 
Lewis Marshall 

### Continuous integration 
- Regularly merge into central repo, aafter automated builds and tests are run 

### Continuous deployment 
- Rpoduce software in short cycles 
- Can be released at any time 

### CICD 
- The combo of these two things iss called CICD 
- Plan 
- Monitor 
- Deploy 
- Release 
- These processes should all be automated

- This joins development and operations teams because they are constantly in contact with each other 
- This is where the term DevOps comes from 

### Tools 
- Jenkins / travis / circleci / argo / go 
- gitlab actions 
- github pipelines 
- bitbucket pipelines 
- aws and azure have their own tools too  

### CICD pipelines 
Design pielines that re a series of jobs that do the actions that they want 

- Tests -- unit / integration / functional (end user perspective - end to end) / code quality - linting and static analysis 
- Build -- packagin (dependencies and containeised) and pushng to private or public registery for deployment 
- Deploy -- Deploy to test environment / stage environment - promote to higher environmen caled staging to validate agaisnt real world data / porduction environment - deployment to production using downtime minimisation strategies

### Automated testing 
Whya are tests automated 

- Early detection of issues - fail fast, shift left principle
- Fast feedback - identify issues before release
- Reliable releases - gain confidence that works as indended, enabled for continjous development 

### Docker 
- Isolation -- contianeration reduces conflict between host machine and container / speeds up deployment
- Versioning - can revert to earlier vesrsion if something goes wrong 
- Consistency - between development environment and production environment 

### Mosdel validation deployment 
Need to ensur tha models are validated 
- Repeatable processes - processes are defiend as code and deployed as Infrastructure as code (IAC) or scripts 
- Packaging - having everything exported as a single artefact we can know that we have consistence 
- Promoition through environments mean that we need to exit approval gates before production 

- Terraform - IAC application -- turns a docker image into = something that runs on AWS etc
- Kubernetes - Handlltiple containers at the same time  

### MLOps
This builds on from Dev ops 

- Design 
- Model development 
- Operations