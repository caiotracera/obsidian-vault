[[AWS|AWS]] has [[Regions]] all around the world, and each region has a specific name, for example *us-east-1*, *eu-west-3* and *sa-east-1*. 

A region can be defined as a cluster of data centers located in a physical space in the real world, like North Virginia (*us-east-1*), Paris (*eu-west-3*) and São Paulo (*sa-east-1*), and most AWS services are region-scoped. That means that if I have a service running in *us-east-1*, the exact same service won't be available in *sa-east-1*.

## How to choose an AWS Region?
Part of the process of launching a new application is to decide which region I should choose. Here are some facts that may impact the choose:

- **Compliance** with data governance and legal requirements: data never leaves a region without your explicit permission;
- **Proximity** to customers: reduced latency;
- **Available services** within a [[Regions|Region]]: new services and new features aren't available in every [[Regions|Region]].
- **Pricing**: pricing varies region to region and is transparent in the service pricing page;

# Availability Zones
The Availability Zones consist of one or more discrete data centers, each with redundant power, networking, and connectivity, and house in separate facilities, so they are isolated from disasters. Each [[Regions|Region]] has many availability zone (usually 3, but the minimum is 3 and the max is 6). For example:

For Sydney region (*ap-southeast-2*), there are 3 availability zones:

- *ap-southeast-2a*;
- *ap-southeast-2b*;
- *ap-southeast-2c*;

# Points of Presence (Edge Locations)
Amazon has more than 400 Points of Presence (400+ Edge Locations & 10+ Regional Caches) in more than 90 cities across more than 40 countries, and that is very helpful to deliver content to end users with lower latency.