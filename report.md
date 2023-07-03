## This report contains questions which should be improved.


### Answers which not meet the expectations

### Date June 27

```
question: give me a numbered list with dates about decision on devflows?
answer: There is no information available about decisions on devflows.
id: 1d0305866c001a37009bbfafbd9a76e3
```

Slightly changed the question and asked again
```
question: give me a  list of decision on devflows?
answer: 	Here are some decisions on DevFlows: 
1. Only 408, 429 and 503 error codes should result in retries (source: 3). 
2. Support data ingestion in batches using DevFlows batch capability (source: 6). 
3. Implement the s3-receive-events INPUT node in M1 first (source: 8). 
4. Provide a lesson for each assignment explaining the relevant concepts required to build the flow (source: 9). 
5. Provide full access to the Workspace account via the Workspace Profile (source: 10). 
6. Bet fully on AWS - Lambda for serverless compute and SNS or EventBridge for eventing (source: 13). 
7. Upgrade the flow to the latest compatible PATCH release, and redeploy, but give the flow developer control (source: 14). 
8. Make the Connector Profile a first-class citizen in DevFlows (source: 18).
id: 7a2101eafdd6697bcdb6ae66f3bf62cd

```
Comment: Lots of information is lost from ans when asked for numbered list with dates
Checked the trace, the chunks are fine but in the reduce step it is not able to extract the information


### Date June 26

```
question: what is devflows? 
answer: I am not able to answer your question at the moment.
id: 5330c16afc012a36df317ec8c770e006 
```
Checked the traces, here also the chunks contains devflows but we are not able to extract the information 


### Date June 16

```
question: LIst the AWS services that Devflows uses
answer: Devflows uses AWS services such as Lambda and SNS.
id: b73f4c756b2665c149bcbbd4389bf4ea

comment: poor quality answer
Expected answer: Devflows uses the following AWS technologies: AWS APIs, Kinesis, Glue, Firehose, S3, Core Actions, HTTP action, Lambda functions, Step Functions, Fargate, Knative eventing (Kafka), SNS, EventBridge, Parameter Store, IAM roles and policies, and Docker images for Lambda functions.
```

```
question: Give me a bullet point list of all decisions to use Aws Lambda to build Devflows with the date on which the decision was made.
answer: There is no bullet point list of all decisions to use AWS Lambda to build Devflows with the date on which the decision was made.
id: f557e747218b445390ed428e3c7b5051

Comment: Retried the same question and got proper answer
answer: 
Decisions to use AWS Lambda to build Devflows were made on the following dates:
- On February 22, 2021, it was decided to move to Lambda and build DevFlows Actions so they can be deployed as Typescript functions in Lambda with the proxy functionality built into a Lambda Layer (source: 2).
- On the same day, it was decided to use AWS services, including Lambda, SNS, etc. (source: 3).
- On February 26, 2021, it was decided to use AWS Lambda global variables (source: 6).
- On February 22, 2021, it was decided to use Lambda and Fargate ECS (source: 9).
- On February 22, 2021, it was decided to change the programming model to be an API model in TypeScript, deploy in Lambda, and handle the DevFlows platform work in a Lambda layer (source: 11).
- On February 10, 2021, it was decided that moving off of Knative and onto Lambda would help (source: 20).
id: 66e1511b1e24783553a9a124e503ef3b
```
Again, chunks are there but the information was not extracted.

Tried the above question without asking for dates and it did a good job
```
question: Give me a bullet point list of all decisions to use Aws Lambda to build Devflows
answer: 
- IT developers, Growth Engineers (in Marketing), FP&A Analysts who use VBA and anyone else who develops scripts and code to solve problems can use DevFlows to quickly build applications by stitching together SaaS applications and AWS services in an easy, visual way.
- AWS experts could build solutions using Lambda functions, Step Functions and/or Fargate.
- Rather than try and optimize sidecars, I would build DevFlows Actions so they can be deployed as Typescript functions in Lambda with the proxy functionality built into a Lambda Layer.
- This goes away with the move to Lambda.
- The abstraction is a REST endpoint per Action (where each node can have an action).
- The design of actions being http servers means that to run on Lambda, the abstraction will need to change and every action will need to be updated to be compatible.
- This design works for any node which is a HTTP server. It does not fit with a mode where we want to deploy in Lambda.
- We need a higher level abstraction that can be applied either to deployment of containers or serverless Lambda functions.
- The CN rebuild of invocables to work on Lambda introduced the concept of “functions”.
- Use AWS Lambda global variables
- DB connection pooling using lambda global variables is easy to implement and, with sensible defaults, can scale to 100+ concurrent lambda invocations.
- ScaleArc provides connection pool support but also requires management overhead.
- A DevFlows deployment would manually require setting up a ScaleArc cluster and performance tuning.
- Additionally, a rough benchmark between a ScaleArc cluster (with 1 server and default settings) vs. using lambda global variables indicated that ScaleArc generated significantly higher error rates (i.e. connection timeouts).
- Using these libraries requires the Lambda code to be written using Node.js.
- This spec uses a lambda function to query an RDS RDBMS based on the provided connection settings.
- It provides data to the flow in an event stream of 1 row per event.
- The system uses Lambda global variables and open-source libraries to support connection pooling.
- It only supports MySQL and PostgreSQL based on availability of open-source libraries, but other databases can be supported by extending these libraries relatively easily.
- The change to run actions in Lambda in preference to Knative Serving
- Execution duration is longer than 15 minutes
- Memory requirement is greater than 10GB
- CPU requirement is greater than 6 vCPU
- I/O requirements are very high
- Support data ingestion in batches using DevFlows batch capability
- Batch_Size is set and controlled at the platform level but each action can set an upper limit on Batch_Size, based on the largest batch it can handle.
- The default value for Batch Window is 60 seconds (1 min), configurable for each workspace.
- Use __bulk_ in data ingestion requests for bulk update.
- Build a scheduled Lambda function, triggered by EventBridge rules, to poll feed destinations.
- Prioritize Lambda implementations.
- Make long running applications be separately deployed outside of the core of DevFlows, but allow communication with them by writing Lambda wrappers that can make the external HTTP requests.
- Have DevFlows actions call an API to generate events.
- The approach though the team is taking with the introduction of Lambda support is to make each proxy be a Lambda function, which then synchronously calls the action as a second lambda function.
- Change the programming model to be an API model in TypeScript, deploy in Lambda, and handle the DevFlows platform work in a Lambda layer.
- Using this model the DevFlows platform would be free to combine multiple Actions into a single Lambda function as an optimization.
- Bet fully on AWS - Lambda for serverless compute and SNS or EventBridge (needs a deeper dive with AWS) for eventing. This transformation is currently being executed by the DevFlows Code Nation team with a focus on Lambda and SNS, though the plan is to keep Kubernetes also.
- Move the programming metaphor for Actions (invocables) to be functions rather than REST endpoints. This would make it easier to run the proxy logic in the same instance as the Action, would allow us to optimize and combine different functions into a single runtime activity and would standardize our Action development on a single language (Typescript). The Lambda change currently occurring will add a function paradigm, but will preserve the existing approach in parallel.
- Re-platforming from Knative eventing to AWS SNS and from Knative serving to Lambda functions.
- Schedule time with AWS to get deep on whether SNS or EventBridge make the most sense here.
- Reportedly the EventBridge team said we should use their service over SNS, but the SNS team may say the exact opposite.
- Use existing 429 handling and exponential backoff to throttle resource consumption.
- Constrain AWS resource usage at certain levels.
- Batch events when they backup.
- Allow adapters to process batches.
- Use AWS services - AppFlow, Step Functions, EventBridge, Lambda, etc - to build their own data flows.
- DevFlows provides a simple UI and abstracts all the plumbing away from the user, automating provisioning and monitoring.
- Using AWS services directly requires a much more technical user who can handle these concerns.
- DevFlows has recently undergone a major change from Knative to Lambda functions and SNS topics to provide the runtime and inter-node communications.
- Automatically determine and use the best execution environment for each action in a flow (i.e. Lambda vs Kubernetes), to provide scalability while avoiding the execution time hard limit of Lambda.
- Actions are packaged as Docker containers, so that they are portable between both Kubernetes and Lambda.
- Use a Proxy Lambda function to provide a standard interface to actions via an SNS topic for passing events between nodes.
- Expose public HTTP endpoints using API Gateway, and use AWS services for other supporting functionality.
- Use INPUT nodes to receive pushed events into flows
- Call AWS APIs directly to create resources needed for an input node
- Include only a Lambda Listener
- Create SQL Actions, which will include drivers to the most common databases - such as Oracle, MySQL, SQL Server, and PostgreSQL
- DevFlows currently uses one single AWS account for all workspaces in a given installation.
- Our throttling approach will reduce concurrent Lambda invocations through batching and reducing the number of proxies.
- Our AWS Accounts approach will allow each workspace to have its own AWS Account, reducing the noisy neighbor problem of one flow interrupting others.
- In the event that concurrency limits are still reached under load, the primary concern is http requests from external sources that may not have retry logic.
- API limits are a normal way of handling these types of increases in API level access.
id: 75f927438ecad499aa605a3a45d7ba3b

```
Comment: Why so much change in answer when we ask with dates and without?



```
question: What is AWS Lambda ?
answer: I don't know.
id: 656a6ffae686c4849e282491ed04b047

```
Comment: after retrying it answers it
The chunks contained the word AWS only once, but lambda is mentioned a lot of times.
Again reduce prompt is not working 



### Date: June 15

```
question: Give me a bullet point list of all decisions to use Aws Lambda to build Devflows with the date on which the decision was made.
answer: 
Decisions to use AWS Lambda to build Devflows:
- Move to Lambda to optimize sidecars and build DevFlows Actions as Typescript functions in Lambda with proxy functionality built into a Lambda Layer (2021-02-22) [2]
- Choose AWS services and focus on Lambda deployments (No date given) [3]
- Use AWS Lambda global variables (2021-02-26) [6]
- Use Lambda and Fargate ECS (No date given) [9]
- Change the programming model to an API model in TypeScript, deploy in Lambda, and handle the DevFlows platform work in a Lambda layer (2021-02-22) [11]
- Bet fully on AWS with a focus on Lambda and SNS (No date given) [12]
- Re-platforming from Knative eventing to AWS SNS and from Knative serving to Lambda functions (No date given) [13]
- Moving off of Knative and onto Lambda (2021-02-10) [20]

id: e9f71f5d91d635279438e93a73be47b9

Comment: we get the source numbers and (No date given) but date exists for all the documents. 
```

### Date: June 11

```
question: Was fargate ever considered as an alternative to Devflows?
answer: Yes, Fargate was considered as an alternative to Devflows.
id: 529dbb4a85bd621edc9c0e7d9c023011

feedback: 6 document links to look through to find out where it was considered as an "Alternative", is a lot. The real value is not from seeing a list of documents that mention Fargate, rather it should list the document where it was considered as an alternative. Ideally there should be none, because Fargate wasn't really an alterative, however if it misunderstaood somethign that is fine, it should just be easier for the user to pinpoint the spot.

Comment: Tried again, still gives similar answer
new id: 2b6ea6fec4073e3cf68f7b406c5c4cf0
```

### Date: June 8

```
question: Who is Arleif Braganza?
answer  : I don't know who Arleif Braganza is.
id: b4f9aefcbfd766df1daec305a02f37af

Comment: Tried the question again twice, still returns "The documents do not provide information on who Arleif Braganza is." but if the question was "List documents which mentions Arleif" then it finds the documents.
new id: 80841191d7d9693ee2cd884328b819a9
```
Here also, "Arleif Braganza" was mentioned in the chunks but was not picked.
tempo link: https://grafana.misc.k8.devfactory.com/explore?orgId=1&left=%7B%22datasource%22:%22KeQoXQEVk%22,%22queries%22:%5B%7B%22refId%22:%22A%22,%22datasource%22:%7B%22type%22:%22tempo%22,%22uid%22:%22KeQoXQEVk%22%7D,%22queryType%22:%22traceql%22,%22limit%22:20,%22query%22:%2280841191d7d9693ee2cd884328b819a9%5Cr%5Cn%22%7D%5D,%22range%22:%7B%22from%22:%22now-7d%22,%22to%22:%22now%22%7D%7D


```
question: What decisions have been made around the use of REST and GraphQL?
answer  :  	The hiring platform requests a candidate examination via a REST API in API Gateway. Option 2 is selected because this is a simple use case with a simple access pattern, suited to REST than to GraphQL.
id: fd88faaa42934b249df569bd637c95f8

comment: From user pov what is "option 2" in answer is not known but we also provide the source which contains it.
```
