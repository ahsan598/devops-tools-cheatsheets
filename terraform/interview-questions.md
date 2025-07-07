This section will prepare you for some common Terraform questions often asked during interviews:

### 1. What is Terraform and its importance in IaC?

Terraform is an open-source IaC tool that provisions and manages infrastructure using a declarative configuration language (HCL). It ensures consistency, speed, and repeatability by defining infrastructure as code.


### 2. What's the difference between terraform plan and terraform apply?

Terraform plan shows you what changes will occur when you run the apply command (a dry run). terraform apply actually implements those changes.


### 3. What is the Terraform State File and what's its purpose?

The state file records the current state of the infrastructure managed by Terraform. It helps Terraform map real infrastructure to your configuration, detect drift, and understand dependencies.


### 4. How do you manage sensitive data (like API Keys) in Terraform?

By using environment variables (TF_VAR_), Terraform Cloud/Enterprise, or external secret management tools like HashiCorp Vault.


### 5. What are Modules and why do you use them?

Modules are containers for reusable Terraform configurations. They help organize code, reduce duplication, and promote consistency.


### 6. What are Implicit and Explicit Dependencies in Terraform?

Implicit Dependency: When one resource uses an output from another resource (Terraform automatically detects the dependency).

Explicit Dependency: When you manually define a dependency using the depends_on meta-argument (when Terraform can't automatically detect it).


### 7. How does Terraform differentiate from other IaC tools like CloudFormation or Ansible?

CloudFormation: AWS-specific, whereas Terraform is cloud-agnostic (supports multiple providers).

Ansible: Primarily for configuration management (installing software, changing configs), while Terraform focuses on infrastructure provisioning.


### 8. Why do you use State Locking in Terraform?

State Locking prevents multiple users from writing to the state file simultaneously, preventing state corruption and race conditions. This is crucial with remote backends.