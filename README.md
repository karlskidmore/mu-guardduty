# mu-guardduty
mu extension for AWS GuardDuty. **UNDER DEVELOPMENT**


Sample usage: 

```

parameters:
  mu-vpc-acceptance:
    ThreatIntelSetUrl: https://s3.amazonaws.com/delete-pmd-guardduty/GuardDutyIpSet.txt
    IpSetUrl: https://s3.amazonaws.com/delete-pmd-guardduty/GuardDutyThreatIntelSet.txt

extensions:
- url: https://github.com/stelligent/mu-guardduty/archive/v0.2.zip
```
