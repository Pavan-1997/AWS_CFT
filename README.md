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
# Creating a S3 Bucket using CFT and checking Drifts:

1. Goto AWS Console -> Search and open AWS CloudFormation

2. Click on Create stack

3. Select the Template is ready

4. Now use Upload a template file

```
AWS_CFT.yml
```

5.  Click on next

6. Provide a name for the Stack

7. Click on next and submit

8. Now go to the S3 buckets and verify the bucket created you will see two of them, one that you have created and other is CFT creates for storing the templates

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/cae09598-6195-4014-80d1-da49ae0d59e3)

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/490ab52b-3611-4ad0-ac85-1e7cb97c141e)

9. Now delete the S3 bucket that has been created 

10. Now goto Stacks and Click on Drifts

11. Click on Detect stack drifts

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/842cdc84-9d04-4534-a934-3c41252cc278)

12. Now goto Stacks -> Stack details -> Stack actions -> Click on View drift results, which shows again the same page because the bucket has been deleted

---
# Creating a S3 Bucket with Versioning using CFT and checking Drifts:

1. Goto AWS Console -> Search and open AWS CloudFormation

2. Click on Create stack

3. Select the Template is ready

4. Now use Upload a template file in the repo

```
AWS_CFT_S3.yml
```

6.  Click on next

7. Provide a name for the Stack

8. Click on next and submit

9. Now go to the S3 buckets and verify the bucket created you will see two of them, one that you have created and other is CFT creates for storing the templates

10. Now go to S3 bucket that has been created -> Goto Properties

    Now you can see that the Bucket Versioning is Enable
   
![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/a0e9b174-d2c4-457e-9599-f6dcfe1f2705)

11. Now manually change the Bucket Versioning to Suspend to check the Drifts

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/7633246a-852f-4de1-b74d-afcf01c930b5)

11. Now goto Stacks and Click on Drifts

12. Click on Detect stack drifts

13. Now goto Stacks -> Stack details -> Stack actions -> Click on View drift results, should see as below

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/d60f1e97-d174-4a91-bc67-3b96cb2197ea)

14. Now select the Resource drift status and click on  View drift details

    Which clearly shows the bucket version chnage we have done
    
![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/8975a1b1-2d78-44e1-9406-a8c50a1f9e07)

