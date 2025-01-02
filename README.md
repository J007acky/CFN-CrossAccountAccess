# 🚀 **IAM Cross Account Access Users**  

![AWS Logo](https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg)  

## 📖 **Description**  
This project demonstrates cross-account IAM configuration in AWS using three separate AWS accounts. The accounts are referred to as **Account A**, **Account B**, and **Account C**. Below are the deployment details for each account:  

---

### 🌟 **Account A**  
#### 👤 **IAM User: Bruce**  
- **Permissions**:  
  - 📝 Read/write permissions for **Account B's EC2 Services**.  
  - 🔗 Ability to attach the role `bat-license-to-put` in **Account B** to services.  
  - 📂 Read permissions for objects in the **S3 bucket `contingency-plans`** in **Account C**.  

#### 👤 **IAM User: Clark**  
- **Permissions**:  
  - 🛠️ Full admin access across **Account A**, **Account B**, and **Account C**.

---

### 🌐 **Account B**  
#### 🛡️ **IAM Role/Instance Profile: `bat-license-to-put`**  
- **Permissions**:  
  - ✍️ Write access to the **S3 bucket `contingency-plans`** in **Account C**.  
- **Access**:  
  - ✅ Can be assumed by any EC2 instance in **Account B**.

---

### 📦 **Account C**  
#### 🗂️ **S3 Bucket: `contingency-plans`**  
- **Purpose**:  
  - 📜 Centralized storage for contingency plans.  
- **Access**:  
  - 🔓 Accessible as per the IAM configurations defined in **Account A** and **Account B**.

---

## 🛠️ **Deployment Guide**  

1. **👤 Create IAM Users in Account A**:  
   - Create `Bruce` with the required policies for cross-account access to **Account B** and **Account C**.  
   - Create `Clark` with full admin privileges across all three accounts.  

2. **🛡️ Create IAM Role in Account B**:  
   - Define the `bat-license-to-put` role with the necessary permissions for accessing the **S3 bucket** in **Account C**.  
   - Ensure the role can be assumed by EC2 instances in **Account B**.  

3. **📂 Configure S3 Bucket in Account C**:  
   - Set up the `contingency-plans` bucket with proper bucket policies for read and write access from **Account A** and **Account B**.  

4. **✅ Validate Cross-Account Access**:  
   - Test the defined IAM roles and permissions to ensure users and services can interact as expected.  

---

## ✨ **Key Features**  
- 🔒 Cross-account IAM user and role configurations.  
- ⚙️ Granular access control across multiple AWS accounts.  
- 📂 Secure interaction with an S3 bucket shared across accounts.  

