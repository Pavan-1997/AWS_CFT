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

---

In CloudFormation, we use Templates and Stacks.

- Template: JSON or YAML formatted text file which is a blueprint of your AWS resources.

- Stack: In CloudFormation, you manage resources as a single unit called a Stack. All the resources in a stack are defined by the stack’s Template.

![image](https://github.com/Pavan-1997/AWS_CFT/assets/32020205/3a4f1e5b-ad8f-449c-8870-24059b13329c)


The following are the major components of the template:

```
Description: Enables you to include arbitrary comments about your template. (Optional)

Parameters: Parameters enable you to input custom values to your template each time you create or update a stack. (Optional)

Mappings: Collection of Key-Value pairs which can be used to set values. (Optional)

Resources: Declares the AWS resources that you want to include in the stack. (Required)

Outputs: Declares output values that you can import into other stacks, return in response, or view on the AWS CloudFormation console. (Optional)
```
