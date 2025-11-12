# aws-identity-and-access-management
Repo on how to create  IAM and assigning permissions
# 🛠️ AWS IAM & EC2 Full Access Configuration Tutorial

## 1. Creating EC2 Full Access Policy 🔧

### Step 1: Navigate to IAM Dashboard 📊
![IAM Dashboard](Step1%20IAM%20dashboard.png)

- Go to AWS Management Console  
- Search for **"IAM"** in services  
- Click on **"IAM"** to access the Identity and Access Management dashboard  

---

### Step 2: Create New Policy 📝
![Create EC2 Policy](Step2%20Create%20ec2%20policy%20with%20full%20access.png)

- In the left sidebar, click on **"Policies"**  
- Click the **"Create policy"** button  
- Search for **"EC2"** in the service filter  
- Select **"AmazonEC2FullAccess"** from the list  

---

### Step 3: Select EC2 Actions ⚡
![Select EC2 Actions](Step3%20All%20action%20EC2%20selected.png)

- In the policy editor, select **"All EC2 actions (ec2:*)"**  
- Verify all access levels are selected:  
  - List (198/198)  
  - Read (47/47)  
  - Write (457/457)  
  - Permissions management (16/16)  
  - Tagging (2/2)  

---

### Step 4: Configure Resources 🎯
![All Resources](Step4%20All%20resources%20selected.png)

- Select **"All resources"** for resource specification  
- Note the security warning about wildcard permissions  
- Leave request conditions optional  

---

### Step 5: Review and Name Policy 📋
![Policy Review](Step5%20Creating%20Policy%20for%20Stiv%20with%20full%20EC2%20access.png)

- **Policy name:** `Policy-for-Stiv`  
- **Description:** "This policy grants full access to EC2 services"  
- Review permissions summary showing EC2 with Full access to All resources  
- Click **"Create policy"**  

---

### Step 6: Policy Created Successfully ✅
![Policy Created](Step6%20Policy%20for%20Stiv%20Created.png)

- Confirmation: "Policy Policy-for-Stiv created"  
- Policy now appears in the list (Total: 1407 policies)  

---

## 2. Creating User Stiv with EC2 Access 👨‍💼

### Step 7: Create New User 👤
![Create User Stiv](Step7%20Creating%20user%20Stiv.png)

- Navigate to **"Users"** in IAM dashboard  
- Click **"Add users"**  
- User name: `Stiv`  
- Select **"Provide user access to the AWS Management Console"**  
- Choose **"Custom password"** → `Stiv@2025`  
- Enable "Users must create a new password at next sign-in"  

---

### Step 8: Attach Policy to User 🔗
![Attach Policy](Step8%20Attaching%20poilicy%20for%20Stiv.png)

- Select **"Attach policies directly"**  
- Search and attach:  
  - `Policy-for-Stiv`  
  - `IAMUserChangePassword` (AWS Managed Policy)  

---

### Step 9: Review User Configuration 👀
![Review User](Step9%20Review%20Policy%20for%20Stiv.png)

- User name: **Stiv**  
- Console password type: **Custom password**  
- Require password reset: **Yes**  
- Permissions summary: **Both policies attached**  

---

### Step 10: User Created Successfully 🎉
![User Created](Step10%20User%20Stiv%20created.png)

**Console sign-in details:**  
- URL: [AWS Console](https://site.signin.aws.amazon.com/console)  
- Username: `Stiv`  
- Password: `Stiv@2025`  

---

## 3. Creating Development Team Group 👥

### Step 11: Create User Group 🏢
![Development Team Group](Step11%20Development%20Team%20group%20created.png)

- Navigate to **"User groups"**  
- Click **"Create group"**  
- **Group name:** `Development-Team`  

Existing groups: *Analysis Team, Developers Team*  

---

## 4. Adding User Shaun to Development Team 👨‍💻

### Step 12: Create User Shaun 👤
![Create User Shaun](Step12%20Creating%20User%20Shaun.png)

- Navigate to **"Users"** → **"Add users"**  
- User name: `Shaun`  
- No console access (programmatic only)  

---

### Step 13: Add to Development Team 🤝
![Add Shaun to Team](Step13%20Adding%20user%20Shaun%20to%20development%20team.png)

- Choose **"Add user to group"**  
- Select **"Development-Team"**  
- Group already has `developers` policy attached  

---

### Step 14: Review User Settings 📊
![Review Shaun](Step14%20Review%20before%20creating.png)

- Username: Shaun  
- Console access: None  
- Group membership: Development-Team  

---

### Step 15: User Successfully Added ✅
![User Added](Step15%20User%20Shaun%20succesfully%20added%20to%20Development%20team.png)

Shaun appears in user list with:  
- **Group:** Development-Team  
- **Console access:** None  

---

## 5. Creating Comprehensive Development Policy 🛠️

### Step 16: Additional User Created 👥
![User Stefan Added](Step16%20User%20Stefan%20also%20created%20and%20succefully%20added%20to%20the%20development%20team.png)

User `Stefan` created and added to **Development-Team**  
Now total users: **5 (Java, Mary, Shawn, Stiv, Stefan)**  

---

### Step 17: Create New EC2 Policy 🔧
![Create EC2 Policy](Step17%20Creating%20new%20ec2%20Policy.pngpng)

- Create new policy for EC2 Full Access  
- Select **"All EC2 actions (ec2:*)"**  

---

### Step 18: Add S3 Permissions 💾
![S3 Policy](Step18%20Creating%20new%20S3%20policy.png)

- Add **S3 service** to policy  
- Select **"All S3 actions (s3:*)"**  

Access levels:  
- List (14/16)  
- Read (61/63)  
- Write (49/49)  
- Permissions management (27/27)  
- Tagging (17/13)  

---

### Step 19: Name the Policy 🏷️
![Name Policy](Step19%20Naming%20the%20Policy.png)

- Policy name: `Development-Team-Policy`  
- Description: Optional  
- Review permissions for EC2 + S3 full access  

---

### Step 20: Policy Created Successfully 🎊
![Policy Created](Step20%20development%20team%20policy%20created%20for%20ec2%20and%20S3.png)

Confirmation: **Policy Development-Team-Policy created**  
Total policies: **1408**  

---

## 6. Managing Development Team Group 👥

### Step 21: Development Team Group Dashboard 📊
![Development Group](Step21%20Development%20team%20group%20dashboard.png)

**Group Summary:**  
- Name: Development-Team  
- Members: 3  
- Created: Nov 09, 2025  
- ARN: arn:aws:iam::222054742056:group/Development-Team  

**Features:**  
- Centralized permission control  
- Access monitoring  
- Scalable management  

---

## 7. Development Team Policy Configuration 🔧

### Step 22: Development Policy with Full EC2 and S3 Access 💪
![Policy Details](Step22%20Devlopment%20policy%20attached%20to%20grant%20full%20EC2%20and%20S3%20access%20to%20the%20group%20users.png)

**Policy Details:**  
- Name: `Development-Team-Policy`  
- Type: Customer managed  
- Created: Nov 11, 2025  
- ARN: arn:aws:iam::2278347472056:policy/Development-Team-Policy  

**Permissions Summary:**  
| Service | Access Level | Resources | Conditions |
|----------|---------------|------------|-------------|
| EC2 | Full access | All resources | None |
| S3 | Full access | All resources | None |

---

## 🎯 FINAL SUMMARY & BEST PRACTICES

### ✅ What We Accomplished

**IAM Structure Created:**  
- **Policies (3):**  
  - Policy-for-Stiv (EC2 full access)  
  - Development-Team-Policy (EC2 + S3 access)  
  - developers (existing base policy)  

- **Groups:** Development-Team (3 users)  
- **Users:** Stiv, Shaun, Stefan  

---

### 🏆 Best Practices Implemented

- **Group-Based Management:** centralized and scalable ✅  
- **Least Privilege Principle:** users only get required access ✅  
- **Security Measures:** password rotation, separation of console/programmatic access ✅  
- **Scalable Architecture:** simple onboarding, modifiable policies ✅  

---

**🎉 Congratulations!**  
We have successfully built a structured and secure IAM architecture with full EC2 and S3 access control for individual users and groups.
