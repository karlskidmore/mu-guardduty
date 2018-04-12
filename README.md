# mu-guardduty
[mu](https://github.com/stelligent/mu) extension for [Amazon GuardDuty](https://aws.amazon.com/guardduty/). For more information on how to use mu, see the mu [QuickStart](https://github.com/stelligent/mu/wiki/Quickstart). To learn how to use mu extensions, read: [Create extensions for the mu DevOps on AWS framework](https://stelligent.com/2018/01/31/create-extensions-for-the-mu-devops-on-aws-framework/).

Sample usage: 

```

parameters:
  mu-vpc-acceptance:
    ThreatIntelSetUrl: https://s3.amazonaws.com/delete-pmd-guardduty/GuardDutyIpSet.txt
    IpSetUrl: https://s3.amazonaws.com/delete-pmd-guardduty/GuardDutyThreatIntelSet.txt

extensions:
- url: https://github.com/stelligent/mu-guardduty/archive/v0.2.zip
```

A ThreatIntelSet consists of known malicious IP addresses. You can provide a list of these IP Addresses in a TXT file. An IP set is a list of trusted IP addresses that have been whitelisted for secure communication with your AWS environment. You can provide a list of these IP Addresses in a TXT file. 

# Scope and Lifecycle
This extension runs outside the scope of a deployment pipeline when the environment is provisioned. This means you cannot simply commit new code to your repository for mu to integrate this extension into your environment. Instead, you need to run mu from the command line to upsert the environment. To do this you need to get a list of environments: 

`mu env list`

This provides a list of environments managed by mu in your AWS account. 

If you need to run this extension against an existing environment, you can upsert the environment so that mu merges the changes from this GuardDuty extension to the environment that is defined outside the pipeline. Here's an example:

`mu env up <environment_name>`

# Pricing
Amazon GuardDuty is priced along two dimensions. The dimensions are based on the quantity of AWS CloudTrail Events analyzed (per 1,000,000 events) and the volume of Amazon VPC Flow Log and DNS Log data analyzed (per GB). For more information, see [Amazon GuardDuty Pricing](https://aws.amazon.com/guardduty/pricing/).
