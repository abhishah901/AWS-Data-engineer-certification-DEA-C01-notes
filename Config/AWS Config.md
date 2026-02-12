AWS Conﬁg provides AWS managed rules, which are predeﬁned, customizable
rules that AWS Conﬁg uses to evaluate whether your AWS resources comply
with common best practices. 

For example, you could use a managed rule to
quickly assess whether your Amazon Elastic Block Store (Amazon EBS) volumes
are encrypted or whether speciﬁc tags are applied to your resources. You can
set up and activate these rules without writing the code to create an AWS
Lambda function, which is required if you want to create custom rules. 

The
AWS Conﬁg console guides you through the process of conﬁguring and
activating a managed rule. 

You can also use the AWS Command Line Interface
or AWS Conﬁg API to pass the JSON code that deﬁnes your conﬁguration of a
managed rule.

After you activate a rule, AWS Conﬁg compares your resources to the rule’s
conditions. After this initial evaluation, AWS Conﬁg continues to run
evaluations each time one is triggered. 	


- Conﬁguration changes – AWS Conﬁg triggers the evaluation when any
resource that matches the rule’s scope changes in conﬁguration. The evaluation
runs after AWS Conﬁg sends a conﬁguration item change notiﬁcation.

- Periodic – AWS Conﬁg runs evaluations for the rule at a frequency that you
choose (for example, every 24 hours).