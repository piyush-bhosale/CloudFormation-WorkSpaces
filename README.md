# AWS CloudFormation Template – WorkSpaces Provisioning

## 🖥️ Project Overview

This CloudFormation template automates the provisioning of an **AWS WorkSpace**, a managed Desktop-as-a-Service (DaaS) solution offered by AWS. It enables organizations to quickly deploy **secure, scalable, and cost-efficient virtual desktops** for users within a directory-managed environment.

This setup is ideal for remote teams, dev/test environments, or enterprise desktop provisioning.

---

## 📄 Template Summary

The template creates an **AWS WorkSpace** for a specific user within an existing **AWS Directory Service domain**, such as:
- Simple AD
- AD Connector
- AWS Managed Microsoft AD

---

## ⚙️ Parameters Required

| Parameter    | Description |
|--------------|-------------|
| `DirectoryId` | ID of the AWS Directory (e.g., `d-xxxxxxxxx`) |
| `UserName`    | User for whom the WorkSpace is being provisioned |
| `BundleId`    | AWS WorkSpace bundle ID (e.g., `wsb-xxxxxxxx`) |

---

## 🧱 WorkSpace Configuration

- **Running Mode:** `AUTO_STOP`  
- **Auto-stop Timeout:** 60 minutes  
- **Root Volume Size:** 80 GB  
- **User Volume Size:** 50 GB  
- **Tags:** `Name`, `Environment`

---

## 🚀 How to Deploy

### 1. Upload via AWS Console
- Go to **CloudFormation > Create Stack**
- Upload the file: `aws-workspace-template.yaml`
- Fill in the required parameters

### 2. Deploy via AWS CLI
```bash
aws cloudformation create-stack \
  --stack-name WorkspaceStack \
  --template-body file://aws-workspace-template.yaml \
  --parameters \
    ParameterKey=DirectoryId,ParameterValue=d-xxxxxx \
    ParameterKey=UserName,ParameterValue=johndoe \
    ParameterKey=BundleId,ParameterValue=wsb-xxxxxx
