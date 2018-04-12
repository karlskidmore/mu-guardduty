# mu-guardduty
[mu](https://github.com/stelligent/mu) extension for Amazon GuardDuty. For more information on how to use mu, see the mu [QuickStart](https://github.com/stelligent/mu/wiki/Quickstart).

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
This extension runs outside the scope of a deployment pipeline when the environment is provisioned. To get a list of environments, you type: 

`mu env list`

This will provide a list of environments managed by mu in your AWS account. 

If you need to run this extension against an existing environment, you can upsert the environment so that mu merges the changes from this GuardDuty extension to the environment that is defined outside the pipeline. Here's an example:

`mu env up <environment_name>`

# Pricing
Amazon GuardDuty is priced along two dimensions. The dimensions are based on the quantity of AWS CloudTrail Events analyzed (per 1,000,000 events) and the volume of Amazon VPC Flow Log and DNS Log data analyzed (per GB). For more information, see [Amazon GuardDuty Pricing](https://aws.amazon.com/guardduty/pricing/).
