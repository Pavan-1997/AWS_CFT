# AWS Cloud Formation Templates

AWS CloudFormation is a service that helps you model and set up your Amazon Web Services resources so that you can spend less time managing those resources and more time focusing on your applications that run in AWS. You create a template that describes all the AWS resources that you want (like Amazon EC2 instances or Amazon RDS DB instances), and AWS CloudFormation takes care of provisioning and configuring those resources for you.

Benefits of AWS CloudFormation:

- Simplify Infrastructure Management
- Quickly Replicate Your Infrastructure
- Easily Control and Track Changes to Your Infrastructure

```
FYI

• Creating AWS resources - IAC

• For quick and short  actions - AWS CLI

• CFT supports both JSON and YAML(most widely used, YAML supports commenting, YAML is more readable, less complex and uses indentation)

• CFT also supports Drift Detection(Eg: Created today EC2 and S3 and tomorrow if someone make changes unintentionally, CFT uses a feature called Detect Drift)

• CFT uses stacks to import YAML from external sources
```


In CloudFormation, we use Templates and Stacks.

- Template: JSON or YAML formatted text file which is a blueprint of AWS resources.

- Stack: In CloudFormation, we manage resources as a single unit called a Stack. All the resources in a stack are defined by the stack’s Template.

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/3a4f1e5b-ad8f-449c-8870-24059b13329c)


The following are the major components of the template:

```
Description: Enables us to include arbitrary comments about the template. (Optional)

Parameters: Parameters enable us to input custom values to the template each time we create or update a stack. (Optional)

Mappings: Collection of Key-Value pairs that can be used to set values. (Optional)

Resources: Declare the AWS resources that we want to include in the stack. (Required)

Outputs: Declares output values that we can import into other stacks, return in response, or view on the AWS CloudFormation console. (Optional)
```
---
# Creating a S3 Bucket using CFT

1. Goto AWS Console -> Search and open AWS CloudFormation

2. Click on Create stack

3. Select the Template is ready

4. Now use Upload a template file

5.  Click on next

6. Provide a name for the Stack

7. Click on next and submit

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/cae09598-6195-4014-80d1-da49ae0d59e3)

   Now go to the S3 buckets and verify the bucket created you will see two of them, one that you have created and other is CFT creates for storing the templates
   
![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/490ab52b-3611-4ad0-ac85-1e7cb97c141e)

   
