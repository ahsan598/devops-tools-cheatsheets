# 🌍 Terraform Cheatsheet

### 📖 What is Terraform?
Terraform is an open-source Infrastructure as Code (IaC) tool developed by [HashiCorp](https://developer.hashicorp.com/terraform).
It allows you to define, provision, and manage cloud infrastructure using simple, declarative .tf configuration files.
Terraform supports multiple providers such as AWS, Azure, GCP, Kubernetes, and more.


### 💡 Real-World Example Use Case

Let’s say you want to create:
- A VPC network
- 2 EC2 instances (web servers)
- 1 RDS database and
- Security Groups to allow HTTP traffic

With Terraform, you can write all this in a `.tf` file like:

> EC2 instance example
```sh
resource "aws_instance" "web" {
  ami           = "ami-0abcdef1234567890"
  instance_type = "t2.micro"
  count         = 2

  tags = {
    Name = "WebServer-${count.index}"
  }
}
```

Then simply run:
```sh
terraform init
terraform plan
terraform apply
```

✅ Done! Infra created in minutes — repeatable, version-controlled, and auditable.

---

### 📚 Recommended Resources
- 🛠️ [How to Install Terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
- 📘 [Terraform Official Docs](https://developer.hashicorp.com/terraform/docs)
- 🎥 [Terraform on YouTube - HashiCorp Channel](https://www.youtube.com/c/HashiCorp?themeRefresh=1)
- 🏗️ [Terraform Registry – Modules & Providers](https://registry.terraform.io/)
- 🧪 [Play with Terraform (in-browser demo)](https://developer.hashicorp.com/terraform/tutorials/aws-get-started)

---

### 📦 What's in This Cheatsheet?

| File                                | Purpose                                  |
|-------------------------------------|------------------------------------------|
| `terraform/terraform-commands.md`   | Terraform CLI commands cheat sheet       |
| `terraform/README.md`               | Guide to using Makefile automation       |
| `terraform/interview-questions.md`  | Common Terraform interview questions     |
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

Or use raw CLI commands → [View all Commands](./terraform/terraform-commands.md)

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

👉 [See Full Q&A](./terraform/interview-questions.md) for interview prep.

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