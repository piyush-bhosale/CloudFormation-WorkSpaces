📌 About This CloudFormation Template
This CloudFormation template automates the provisioning of an AWS WorkSpace, a managed virtual desktop (DaaS) solution provided by AWS. It enables administrators to quickly deploy secure, scalable, and cost-effective virtual desktops for their users.

🔧 What the Template Does:
Creates a WorkSpace for a specific user within an existing AWS Directory Service domain (e.g., Simple AD, AD Connector, or AWS Managed Microsoft AD).

Accepts key parameters such as:

DirectoryId: The ID of the AWS Directory the WorkSpace is joined to.

UserName: The user for whom the WorkSpace is being provisioned.

BundleId: The hardware and software configuration of the WorkSpace (e.g., Windows 10, performance specs).

Configures Workspace properties like:

Running Mode set to AUTO_STOP to save costs when not in use.

Timeout set to 60 minutes for auto-stopping the WorkSpace after inactivity.

Disk sizes for root (80 GB) and user volumes (50 GB).

Adds resource tags for better environment tracking (Name, Environment).

✅ Benefits:
Simplifies the creation of AWS WorkSpaces using Infrastructure as Code (IaC).

Fully deployable in AWS CloudFormation Console, AWS CLI, or through CI/CD pipelines.

Enables consistent, repeatable provisioning for enterprise or development environments.

