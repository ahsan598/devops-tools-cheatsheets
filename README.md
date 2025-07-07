# 🌍 Terraform Cheatsheet

This branch contains essential Terraform commands, Makefile automation, and concepts to help you manage Infrastructure as Code (IaC) efficiently.

---

### 📦 What's in This Cheatsheet?

| File                                | Purpose                                  |
|-------------------------------------|------------------------------------------|
| `terraform/terraform-commands.md`   | Terraform CLI commands cheat sheet       |
| `terraform/README.md`               | How to use the Makefile automation       |
| `Makefile`                          | Automates init, plan, apply, destroy     |

---

### 👤 Who Is This Cheatsheet For?

- DevOps Engineers  
- SREs (Site Reliability Engineers)  
- Cloud Engineers working with Terraform  
- Students & professionals preparing for interviews  
- Anyone who needs a quick Terraform reference

---

### 🚀 Quick Start (Core Workflow)

Clone the repo and switch to this branch:

```sh
git clone https://github.com/ahsan598/devops-cheatsheets.git
cd devops-cheatsheets
git checkout terraform
```


Run Terraform actions using Makefile:
```sh
make init      # Initialize the Terraform config
make plan      # Show what will be created/changed
make apply     # Apply the changes
make destroy   # Tear everything down
```

Or use raw CLI commands → [View Commands](./terraform/terraform-commands.md)

---

### 🧠 Key Concepts
- **Providers:** Plugins for interacting with cloud platforms (e.g., AWS, Azure, GCP)
- **Resources:** Infrastructure elements like EC2, S3, VPC, etc.
- **State File**: Keeps track of what's been created
- **Modules:** Reusable Terraform code blocks
- **Variables & Outputs:** For dynamic configuration


### 📄 Cheat Sheet
Terraform [CLI Commands](./terraform/terraform-commands.md)

### ⚙️ Automation
How to Use the [Makefile](./terraform/README.md)

---

### ❓ Frequently Asked Interview Questions
- What is the purpose of terraform init?
- How does Terraform manage state?
- What's the difference between terraform plan and apply?
- What are Terraform modules?
- How can you handle secrets in Terraform?
- Explain terraform workspace usage.

👉 See [terraform/interview-questions.md](./terraform/interview-questions.md) for interview prep.

---

### 🛠️ Some Useful Commands

```sh
terraform init         # Initialize working directory
terraform fmt          # Format configuration files
terraform validate     # Validate configuration
terraform plan         # Preview infrastructure changes
terraform apply        # Apply configuration
terraform destroy      # Destroy infrastructure
terraform state list   # List resources in state file
terraform output       # Show outputs
```