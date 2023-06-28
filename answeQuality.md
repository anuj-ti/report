### Some ways we can incorporate in future for answer quality

It is not able to answer questions like:
- Questions with no entities:
```
  e.g. what products do you know about?
```


- When we ask questions like:
```
    question: "Is AWS Lambda used in the latest version of Devflows?"
    answer: "Yes, AWS Lambda is used in the latest version of Devflows."
```
  I think here it should have added "why" it was chosen also, because all the steps upto extract relevant chunks will remain the same and it has all the required info. to answer "why" as well.
  Like this example:
```
    question: Does Devflows even use AWS Lambda?
    answer: Yes, Devflows uses AWS Lambda for serverless compute and various functionalities.
```


- For questions like:
```
	question: "Does there exist an ITD for Devflows that mentions AWS Lambda and licenses?" 
    answer: "Yes, there exists an ITD for Devflows that mentions AWS Lambda, but it does not mention licenses."
```
   It gives the ITD's in sources, but it would be better if we can add something in the answer like "refer the sources for the documents"
   
   similar example:
```
  id: f22308c2e5578afef4f0c1f0fa2498ae 
  question: Get me the ITDs where AWS Lambda is discussed 
  answer: AWS Lambda is discussed in ITD 3 and ITD HTTP.3.
```


- The answers date format
```
    ... Lambda Layer was made on February 22, 2021 at 16:51:03.206Z. 
```
  Currently the dates in the answer comes in this format.
  We can remove the seconds and miliseconds here because it makes it little messy.


- Some tricky example question was asked similar to "What do you know about"
```
  question:Summarize this database and the kind of questions I can ask 
  answer:This database focuses on AWS services, allowing users to create and delete Topics and Subscriptions via SNS's API, query SNS for lists of available Topics and Subscriptions, and run custom SQL queries using Python scripts. You can ask questions related to AWS database engines, SNS quotas, rate limits, and querying data using SQL
  id: cb49bed4f45465bb201db0561c26750e
```
  similar question: "How many documents have been indexed ? How big is your graph database ?"
- Sometimes the answer contains string like: `"ITD DISCOVERY.1 - Subflows are discovered like actions"` but there are multiple sources for the same
  For such answers we may try to mention which spefific document it is about.
  
  Example:
```
question: Give a bullet point list of decisions in devflows? 
answer:
- Only 408, 429 and 503 error codes should result in retries.
- Setting up a development environment with the right frameworks, libraries and OS packages
- Multiple inputs/outputs - No
- Adapters with Actions (no change)
- A variable can be declared as a string, a number, a boolean, an object or an array
- Configure S3 and Lambda to send S3 event notifications to DevFlows.
- Provide a lesson for each assignment explaining the relevant concepts required to build the flow
- Provide full access to the Workspace account via the Workspace Profile
- Create sub-flow.
- Naming subflows to look like regular actions.
- ITD DISCOVERY.1 - Subflows are discovered like actions.
- Provide tools to make it easy to find invocables.
- We will integrate with AWS AppFlow and EventBridge where connectors are available, consistent with the Cloud Integration Hub Roadmap.
- Don’t worry about current users
- Make the Connector Profile a first-class citizen in DevFlows.
- Modified P2 feedback.
- On a monthly basis, check the list of newly implemented changes and determine if a new badge assignment should be created
- ITD DEFINE.1 - Define subflows through a subflow-interface input node.

id:7d30b1570923b9f2dd502cdc6856c1fa 
```

It gives a lot of sources and also has a point `ITD DISCOVERY.1 - Subflows are discovered like actions.`, now we don't know which specific file has this ITD.