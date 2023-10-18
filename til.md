---
layout: page
title: TIL
---

<p class="message">
  This is a collection of notes and remarks I have compiled about tech. Hopefully, this will prove useful when I want to look back at my tech knowledge. 
</p>

### 17.10.2023 
AWS CloudWatch Log groups can only have two subscriptions with filtering. So, if you need to trigger a Lambda function based on log containing a string, you would have to implement:
1. Create a CloudWatch metric based on a search pattern
2. Create a CloudWatch alarm based of the metric
3. Push notification to SNS on ``IN ALARM`` event
4. Create a Lambda function with SNS trigger
5. Query CloudWatch Logs from the function to get the log line that originally triggered that CloudWatch alarm

### 15.10.2023
`nslookup` and `dscacheutil` might produce different DNS lookup results on MacOS. This is related to the fact that `nslookup` does use MacOS DNS resolvers, while `dscacheutil` does. 

### 12.10.2023
 Not that many Docker images are built for `arm v7` architecture. Thus, I have to rebuild every Docker image I want to use on my home lab Kubernetes cluster locally.   