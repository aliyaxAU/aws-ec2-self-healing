# AWS EC2 self-healing 

In this small project i will be creating two different failure scenarios to demonstrate how the Auto Scaling Group responds to both instance‑level and Availability Zone‑level failures.

## Scenario 1 Instance Failure (Same AZ Replacement)

The scenrio demonstrates if one of ec2 instance withing the same AZ is terminated, Auto Scaling will detect the issue and launch a new instance in the same Availability Zone.

Explore a failure scenario: [Instance failure same AZ](https://github.com/aliyaxAU/aws-ec2-self-healing/blob/main/03-test-instance-failure-same-AZ.md)

## Scenario 2 — Availability Zone Failure (AZ Replacement)

This scenario replicates where an entire AZ becomes unavailable detects that the existing instance was running in an AZ it was no longer allowed to use and launches a new instance in the remaining healthy AZ.

Explore a failure scenario: [Availability Zone Failure](https://github.com/aliyaxAU/aws-ec2-self-healing/blob/main/04-test-availability-zone-failure.md) 

Scenario | Trigger | ASG Response | Result
-| -| -| -|
|EC2 Instance failure | Terminates/Unhealthy | A new EC2 Instance is launched in the same AZ | Self healing at instance level |
|AZ failure | AZ Removed/Unavailable | A new EC2 Instance is launched in a different AZ | High availability across AZs
