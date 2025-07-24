# Cloud Governance Gone Rogue – Azure Policy Lab

### Course: CST8919 – DevOps Security and Compliance  
### Lab – Enforcing Organizational Policies in the Cloud  
---

## Scenario

Welcome to **MapleTech Solutions**, a rapidly growing Canadian cloud-native company.

You’ve just been hired as a **Cloud Security Engineer**, and during your onboarding, you're told:

> “Developers are deploying resources across the globe, exposing public IPs, and skipping tags. We need order. Lock things down and enforce our cloud compliance policies — starting today.”

Your mission is to bring **governance, security, and compliance** to Azure using **Azure Policy**.

---

## Lab Objectives

- Create and assign **Azure Policies** and a **Policy Initiative**
- Enforce:
  - Region restriction to **Canada Central**
  - Mandatory tagging (`ProjectName`)
  - No public IP addresses
- Test enforcement with sample deployments
---

## Part 1: Define the Guardrails

You will create **three custom Azure Policies**.

### Policy 1: Region Lockdown
- **Name**: `Only-CanadaCentral`
- **Effect**: Deny
- **Description**: Denies any resource that is not being deployed in the `Canada Central` region.

### Policy 2: Mandatory Tagging
- **Name**: `Require-ProjectName-Tag`
- **Effect**: Deny
- **Description**: Requires all resources to include a `ProjectName` tag.

### Policy 3: Block Public IPs
- **Name**: `Deny-Public-IP`
- **Effect**: Deny
- **Description**: Prevents creation of Public IP addresses.

---

## Part 2: Group Policies into an Initiative

### 🔹 Create a Policy Initiative:
- **Name**: `MapleTech Secure Foundation`
- **Add all three policies** you just created.
- **Category**: `Security` or `Compliance`

---

## Part 3: Assign the Initiative

- Assign the initiative to a **resource group**.
- Ensure the **enforcement mode** is set to `Enforce` (deny).

---

## Part 4: Simulate Developer Activity

Test the enforcement of your policies by simulating typical developer behavior.

### Test Cases

| Action | Expected Outcome |
|--------|------------------|
| Deploy VM in **East US** | ❌ Denied |
| Deploy Storage Account **without `ProjectName` tag** | ❌ Denied |
| Create a **Public IP** | ❌ Denied |
| Deploy VM in **Canada Central** with tag | ✅ Allowed |

Take **screenshots** of each attempt and result.

## Part 5: Create a 10-Minute Video Demo

Record a max **10-minute video** where you:

1. Explain the scenario and what policies you created.
2. Show the policy definitions in the Azure Portal.
3. Demonstrate the test cases both failed and successful deployments.
4. Highlight how Azure Policy enforced the rules.
5. Conclude with your takeaways.
---

## Submission Checklist

Create a folder in your GitHub repo called `/policy-lab` and include:

- `screenshots/` folder with key screenshots
- `policy-definitions/` folder with JSON files for your custom policies
- **Video demo link** (in `README.md`)
- A short `README.md` with:
  - Summary of the lab
  - Explanation of each policy
  - Challenges and lessons learned

---