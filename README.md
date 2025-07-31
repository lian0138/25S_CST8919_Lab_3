# Azure Policy Lab - MapleTech Solutions

## Summary of the lab
In this lab, I implemented Azure Policy guardrails for MapleTech Solutions to enforce cloud compliance by restricting resource deployment to the Canada Central region, requiring a `ProjectName` tag, and blocking public IP creation. By grouping these policies into a single initiative and assigning it to a resource group, I ensured consistent and automated enforcement of organizational security standards.

## Explanation of each policy

**Only-CanadaCentral:** This policy denies the creation of any Azure resources outside of the Canada Central region to enforce data residency.

**Require-ProjectName-Tag:** This policy blocks the deployment of any resource that does not include a `ProjectName` tag, ensuring proper tagging for management and compliance.

**Deny-Public-IP:** This policy prevents the creation of public IP addresses to reduce external attack surfaces and enhance cloud security.

## Challenges and lessons learned
One challenge was making sure policies were specific enough to enforce compliance without disrupting essential developer workflows or existing resources. Through this lab, I learned the importance of carefully testing policies in a controlled environment to ensure they provide security and governance while still supporting business productivity.

## Video Demo
https://www.youtube.com/watch?v=yBLAs9ONHqg

## Screenshots
![enter image description here](https://raw.githubusercontent.com/lian0138/25S_CST8919_Lab_3/refs/heads/main/screenshots/initiativeDefinition_1.png)
![enter image description here](https://raw.githubusercontent.com/lian0138/25S_CST8919_Lab_3/refs/heads/main/screenshots/initiativeDefinition_2.png)
![enter image description here](https://raw.githubusercontent.com/lian0138/25S_CST8919_Lab_3/refs/heads/main/screenshots/assignInitiative.png)


