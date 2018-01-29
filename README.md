# mu-guardduty
[mu](https://github.com/stelligent/mu) extension for Amazon GuardDuty. For more information on how to use mu, see [QuickStart](https://github.com/stelligent/mu/wiki/Quickstart)

Sample usage: 

```

parameters:
  mu-vpc-acceptance:
    ThreatIntelSetUrl: https://s3.amazonaws.com/delete-pmd-guardduty/GuardDutyIpSet.txt
    IpSetUrl: https://s3.amazonaws.com/delete-pmd-guardduty/GuardDutyThreatIntelSet.txt

extensions:
- url: https://github.com/stelligent/mu-guardduty/archive/v0.2.zip
```

# Pricing
Amazon GuardDuty is priced along two dimensions. The dimensions are based on the quantity of AWS CloudTrail Events analyzed (per 1,000,000 events) and the volume of Amazon VPC Flow Log and DNS Log data analyzed (per GB). For more information, see [Amazon GuardDuty Pricing](https://aws.amazon.com/guardduty/pricing/).
