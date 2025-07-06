# 🛠️ Terraform Commands Cheat Sheet

This is a simple reference for common Terraform CLI commands, perfect for quick use or interview prep.

---

## ✅ Basic Commands

| Command | Description |
|--------|-------------|
| `terraform init` | Initialize Terraform in your directory |
| `terraform validate` | Check for syntax/config errors |
| `terraform plan` | See what changes will be made |
| `terraform apply` | Apply the changes to infrastructure |
| `terraform destroy` | Delete all resources Terraform manages |

---

## 🧠 Workspace Management

| Command | Description |
|--------|-------------|
| `terraform workspace new <name>` | Create a new workspace (e.g., dev/prod) |
| `terraform workspace list` | List all workspaces |
| `terraform workspace select <name>` | Switch to another workspace |
| `terraform workspace show` | Show current workspace |
| `terraform workspace delete <name>` | Delete a workspace |

---

## 🗂️ State Management

| Command | Description |
|--------|-------------|
| `terraform show` | View state and output values |
| `terraform state list` | List resources in the state file |
| `terraform state mv <old> <new>` | Rename/move a resource in state |
| `terraform state rm <resource>` | Stop tracking a resource |

---

## 📦 Modules

| Command | Description |
|--------|-------------|
| `terraform get` | Download required modules |
| `terraform get --update` | Update modules to latest version |

---

## 🔁 Import Existing Resources

| Command | Description |
|--------|-------------|
| `terraform import <type>.<name> <id>` | Import real infrastructure to Terraform |

---

## 📤 Output Management

| Command | Description |
|--------|-------------|
| `terraform output` | Show output variables |
| `terraform refresh` | Sync state with actual infrastructure *(deprecated)* |

---

## 🎨 Formatting & Docs

| Command | Description |
|--------|-------------|
| `terraform fmt` | Format your code |
| `terraform-docs markdown .` | Generate Markdown docs from Terraform code |

---

## 🔍 Bonus Commands

| Command | Description |
|--------|-------------|
| `terraform graph` | Generate resource dependency graph |
| `terraform taint <resource>` | Mark a resource for recreation |
| `terraform untaint <resource>` | Cancel a taint |
| `terraform version` | Show current version |
| `terraform providers` | List all used providers |

---

## 📚 Pro Tip

Use `make` or shell scripts to group commands into reusable automation tasks!

