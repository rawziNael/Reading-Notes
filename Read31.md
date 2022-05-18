# Read: 31 - Espresso  

#### What is AWS Amplify? Pros and Cons?  

AWS Amplify is a powerful toolkit developers use to build full stack applications that directly integrate with the cloud. Using it, developers can rapidly setup, test,
launch, and scale production ready applications with minimal time spent focusing on the details.  

#### What is AWS Amplify? 

Amplify offered something these other product’s didn’t: direct feature integration with AWS’ powerful backend services.  
In essence, AWS Amplify is a toolchain that helps you build and deploy entire applications very quickly. Typically, this Amplify is mainly aimed at full stack
applications,but you can also use it just for its ability to generate a backend.  

In terms of usage, we primarily use AWS Amplify as a Command Line Interface or CLI tool, however, there is a limited feature UI that allows you to do some administration
tasks for some day to day activities. I like to think of the Admin UI as a nice way to visualize the components you’re adding to your application.  

Now the main strength of Amplify is that it quickly lets you add thigs like Storage, Authentication, Monitoring, and PubSub functionalities. Now you don’t need to know
what Amplify is provisioning behind the scenes to add these functions. For example,if you decide to use something like Storage, you may be provisioning one or
more components from a multitude of AWS Services without actually knowing about it.  

Amplify is an attractive tool because it allows developers to add application functionality without having to know what AWS services to use to achieve that functionality.  

All of these features may seem magical, but behind the scenes Amplify is leveraging a relatively old product to quickly let you add new components, a service called AWS
CloudFormation.  

#### An Example Of Amplify Features  

Things like Authentication, Datastores, Functions, and CI/CD offerings. This is a big list of impressive things you can do with Amplify, but behind the scenes there’s
no mystery ere.  
- For example, to achieve user Authentication and Authorization, we rely on Amazon Cognito.  
-  To host APIs, either GraphQL or REST/HTTP based, we use either AWS Appsync or API Gateway, respectively. 
-  For raw object storage including asset files for your web applications, or deployment executables, we rely on the popular Amazon S3.  
-  For asynchronously communicate with other microservices, aka PubSub, we use a combination of Amazon Simple Notification Service (SNS) and Simple Queue Service (SQS).  
-  For analytics, we utilize Amazon Pinpoint.  
-  For domain registration and DNS modifications, we use Amazon Route 53.  
-  To build dashboards, examine logs, and add alarms we use Amazon Cloudwatch.  
-  For Serverless Compute we use AWS Lambda.  
-  And finally, for DataStores, we generally rely on the popular NoSQL Database Amazon DynamoDB.  

#### Usage  

- Command Line Interface (CLI)  

Primarily, you’re going to be interacting with Amplify through the CLI. The CLI is a library that you can install to your terminal to interact with the library.  
To configure a new project, we use the amplify configure and amplify init commands. Amplify will ask you some basic questions about your application configuration
including language, framework, name, and other details.  

- Admin UI  

The Admin UI does have some neat features such as the Data Model Studio. Using it, you can easily add Data Models including their fields and types. Further, you can
add relationships between them similar to building out an ER diagram for a database schema. The cool part is that Amplify will generate model files that you can use
in your application code. The other cool part is that by defining relationships between models, Amplify will automatically generate the correct database indexes to
support relationship style lookup patterns – pretty neat!  

#### Pros and Cons of Amplify  

- Pro # 1 – Getting Started Quickly  
Amplify lets you deploy get started with new projects quickly. You can easily run commands to generate application components quickly to get familiar with their
workings. You can also spend more of your time focusing on the business problems you’retrying to solve instead of worrying about the details of managing your system.  

- Pro # 2 – Fast Development Cycles  
Since Amplify is CLI based, it allows for some very fast development cycles. Developers can take advantage of the toolkit to rapidly experiment with new changes and
deploy them out to the cloud. Gone are the days of waiting minutes or even hours waiting for yourapplication to hit the test or production environment – this can
now happen in seconds. 

- Pro # 3 – Shielding From the Complexity of AWS  
Instead of starting with a problem, and trying to figure out which service(s) to solve that problem, Amplify offers a solution oriented mindset. By offering direct
functions or features as components such as Storage, Authentication, Analytics, and others, developers don’t need to care about which AWS services are being used
behind the scenes, they generally just worry about the end product.  

- Con # 1 – You Don’t ‘Really’ Learn AWS  
Pro # 3 can also be considered a con. A consequence of being shielded from the complexity of AWS is the fact that you don’t really learn AWS. So much about being
a great AWS focused developer is understanding the lower level components and how they inter-operate – Amplify is in complete contrast to this principle.  

- Con # 2 – Collaboration Can Be Frustrating  
Amplify can be used as a solution that allows for many developers to work together on the same project. Buyer beware though, collaboration can be a bit frustration
in terms of deployment collisions. AWS does offer some useful workflows for a collaborative development environment though, however it was still a bit frustrating
trying to collaborate with another dev and stepping on eachother’s changes.  

- Con # 3 – Stepping Outside The Box  
One of the problems with Amplify is that you’re kind of at the mercy of the product features offered through AWS Amplify. If theres a particular AWS service that
you’re interested in using in your Amplify project and its not supported, you may need to manage it separately.  

- Con #4 – Potential For Surprise Bills  
Because services are being provisioned behind the scenes, there is the possibility you can add a functionality that relies on a service with cost implications.  
you should really understand the cost models of services being used by amplify for each functionality prior to adding it to your project. This will help you avoid
surprise bills. I also suggest setting up a billing alert a small dollar threshold ($5 or so should be fine) to get early warnings if your application starts incurring 
some unexpected costs. 






 
