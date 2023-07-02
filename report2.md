## This report contains executions after June 27

### June 27

Problem: the formatting didn't work for this one
```
id: cd23fddae5ea5bf652cd74c65ff2d053
question: give me a list of reasons devflows usage of AWS lambda? 
answer: 
Reasons for DevFlows usage of AWS Lambda include: deploying as Typescript functions with proxy functionality built into a Lambda Layer (1), changing the abstraction to be compatible with Lambda (2), managing efficient connection pooling (3), querying RDS RDBMS (4), handling asynchronous calls (5), creating adapters and customizing OAuth implementation details (6), batching support for better performance (7), building scheduled Lambda functions triggered by EventBridge rules (8), prioritizing Lambda implementations for better performance (10), combining multiple actions into a single Lambda function (11), re-platforming from Knative to AWS services (13), processing large amounts of data (14), supporting non-blocking actions (15), aligning with industry trends (16), building a large standard library of listeners (17), reducing the noisy neighbor problem (18), and moving off of Knative for better performance (19).
```
Reason: The LLM returned an unformatted result


Problem: very short answer
```
id: 6241f75d939f525f4dca72e81d67974b
question: Give me a numbered list of technologies where AWS lambda was used?
answer: 1. AWS Lambda was used with SNS.
```

Problem: It didn't answered the question which it knows
```
id: 80841191d7d9693ee2cd884328b819a9
question: Who is Arleif Braganza?
answer: The documents do not provide information on who Arleif Braganza is.
```
Reason: It was caught in the intermediate step, but not in the combine step
```
intermediate steps: 
[
    " mailto:arleif.braganza@devfactory.com[[.underline]#Arleif Braganza#]",
    " mailto:arleif.braganza@devfactory.com[[.mark]#[.underline]#Arleif Braganza##]",
    " mailto:arleif.braganza@devfactory.com[[.underline]#Arleif Braganza#]"
]
```

### June 28


Problem: 
```
id: 
question: 
answer: 
```
Reason: 


Problem: Didn't answered the question
```
id: 386d2890ab44654af45e3de44d3489ad
question: Who is Arleif Braganza?
answer: I don't know who Arleif Braganza is.
```
Reason: 

When we ask the same question a little differntly then it answered it
```
id: 0de4d7004e3c432820909aa1a60ccd05
question: What are the documents that mention Arleif Braganza ?
answer: Arleif Braganza is mentioned in three documents.
```
Still a problem, why only three?


Problem: Date unknown issue
```
id: 0375bb5b4626d09a9591a11c94a3b785
question: 	Give me a bullet point list of all decisions to use Aws Lambda to build Devflows with the date on which the decision was made
answer: Decisions to use AWS Lambda to build Devflows include: 
- Decision to use AWS Lambda to build Devflows (date unknown) 
- Change in abstraction to run on Lambda (date unknown) 
- Update of every action to be compatible with Lambda (date unknown) 
- Introduction of concept of “functions” to work on Lambda (date unknown) 
- Decision to make each proxy a Lambda function, triggered from SNS and firing the next event to SNS when the action completes (date unknown) 
- Decision to use an API model in TypeScript, deploy in Lambda, and handle the DevFlows platform work in a Lambda layer (date unknown) 
- Decision to combine multiple Actions into a single Lambda function as an optimization (date unknown) 
- Only include a Lambda Listener (Decision made on April 29, 2022) 
- Decision to build DevFlows Actions so they can be deployed as Typescript functions in Lambda with the proxy functionality built into a Lambda Layer (Decision made on February 22, 2021) 
- Decision to build a scheduled Lambda function, triggered by EventBridge rules, to poll feed destinations (Decision made on March 9, 2021) 
- Decision to prioritize Lambda implementations and make long running applications be separately deployed outside of the core of DevFlows, but allow communication with them by writing Lambda wrappers that can make the external HTTP requests (Decision made on February 22, 2021) 
- Decision to bet fully on AWS - Lambda for serverless compute and SNS or EventBridge for eventing (Decision made on February 22, 2021) 
- Decision to re-platform from Knative eventing to AWS SNS and from Knative serving to Lambda functions (Decision made on February 22, 2021)
```
Reason: 


Problem: It didn't answered the question when asked with date, without date it answered + Randon source numers issue

With date:
```
id: 1d0305866c001a37009bbfafbd9a76e3
question: 	give me a numbered list with dates about decision on devflows?
answer: There is no information available about decisions on devflows.
```

Without date:
```
id: 7a2101eafdd6697bcdb6ae66f3bf62cd
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
```


Problem: It didn't had any info about devflows
```
id: f8cba74508c3291e3ba516cac8331cff
question: 	what is devflows?
answer: Apologies, but I couldn't find any relevant information regarding your question. It is possible that this space doesn't contain the required documents to answer your question.
- This space contains technical spec documents of a product called devflows belonging to ESW organization.
Example queries you could try:
- What is devflows?
- Why does devflows use Lambda?
- Give me a bullet point list of technologies used by devflows.
- When did devflows first decide to use Lambda in its infrastructure?
```

Same for this execution as well
```
id: 3913276cc5f1369a7e6501bdb5587f54
question: What AWS technologies do you know about ?
answer: 	Apologies, but I couldn't find any relevant information regarding your question. It is possible that this space doesn't contain the required documents to answer your question.
- This space contains technical spec documents of a product called devflows belonging to ESW organization.
Example queries you could try:
- What is devflows?
- Why does devflows use Lambda?
- Give me a bullet point list of technologies used by devflows.
- When did devflows first decide to use Lambda in its infrastructure?
```
Reason: 


Problem: Didn't answered the question
```
id: b4c2048c12d1bfa35898747ee33cfb4c
question: what aws technologies you know?
answer: I don't know.
```
Reason: 