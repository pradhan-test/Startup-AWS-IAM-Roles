# IAM Roles for Startups



## Motivation

Many startups are now setting up on AWS infrastructure, but it’s long before they figure out the importance of IAM’s role. To be fair, it’s of least importance initially, as the necessary time and energy are hard to justify. Rather, businesses should first focus on the product itself. But imagine if there was a hand holding the business owner, making the setup of IAM roles expedient and easy. After all, security is your priority at the outset. Let alone startups, even midsize and some large companies make this crucial mistake and accumulate large tech debt.

This project focuses on creating a skeleton of IAM roles for startups, with the ability to get started with little or no modifications. The project focuses on multi-size startups:

- Small - 5 people
- Midsize - ~12 people
- Large - 40 or above

Follow Us On [![alt text][2.1]][2]

[2.1]: http://i.imgur.com/P3YfQoD.png
[2]: http://www.facebook.com/SingaporeTechEntrepreneurs/

## Role of Security

In this project, we try to place security above everything. We are trying to avoid accidental deletions. We are assuming that every team member will log in from known IPs. As an added layer of security, we are making MFA mandatory for every user that logs in, even admins. To add the mandatory MFA, there is a policy called ```forceMfa.json``` that will need to be created and added to a group called ```FORCE_MFA```. Each IAM user to be created, will need to be a part of the ```FORCE_MFA``` group. This policy will deny IAM user's access to AWS resources until they add their MFA and use it to authenticate.

## Assumptions

We are working with the following assumptions:

Presence of generic job roles.
In case an employee is wearing multiple hats, make sure you update accordingly. We have tried to block certain destructive actions like bucket deletion, accidental terminations for users who are not AWS admin like frontend and backend engineers.
Use of blacklist instead of whitelist to keep the roles tidy.

## Job Profiles

We are considering job profiles across different verticals, i.e: business, finance, tech and ops.

read [ROLES.md](https://github.com/Singapore-Tech-Entrepreneurs/Startup-AWS-IAM-Roles/blob/master/ROLES.md) for role and its assumption details.

## Setting Up Roles

Create groups based on job profiles and attach policy documents from this project. Then create users and assign them to these groups.

## Contributing

- Fork it!
- Create your feature branch: git checkout -b my-new-feature
- stage your feature: git add <changed_file>
- Commit your changes: git commit -m 'feat: add new feature' -m 'add my-new-feature, use it as: my-new-feautre(args)' -m 'closes #26'
- Push to the branch: git push origin my-new-feature
- Submit a pull request :D


## Contributors

- Padmakar Ojha @dvopsway
- Michael Amurjuev @LawTech Enthusiast
- Kj Venky @kjvenky
