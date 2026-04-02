# Test Instance failure (same AZ)

This implementation shows how the Auto Scaling Group responds to instance‑level failure.

After I complete setting up the autoscaling group and launching the template, I will check to see if the instance is running:

In EC2 Dashboard I will select Instances and confirm the ASG created one instance. I click on instance and copy the instance PUBLIC IP in browser and confirm I'm seeing:

![alt text](<img/ensure instance public ip runnig.png>) 

![alt text](<img/ec2 instance running.png>)

## Simulate the issue

I am going to terminate the instance and within 10-30 seconds the autoscaling group should detect and replcace with a new instance.

the current instance is from http://54.209.128.161/ and zone is `us-east-1b`.

![alt text](<img/shutting down the instance.png>)

Veryfying that the new instance got created and confirm this is a new instance public IP is different:

![alt text](<img/creates a new ec2.png>)

New instance with public IP `3.84.163.135`

![alt text](<img/new ec2 instance.png>)

## Summary

The AZ itself is healthy, so ASG simply replaces the instance inside the same zone.

Self‑healing works on the instance level. In addition, there is less downtime, and no manual action is needed.