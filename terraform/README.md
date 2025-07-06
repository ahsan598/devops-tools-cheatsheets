## ⚙️ Terraform Automation with Makefile

Managing Terraform can involve typing the same long commands repeatedly. To save time and avoid mistakes, we’ve added a Makefile to this project. This helps automate Terraform tasks like init, plan, apply, destroy, and more — using short, consistent commands.


### 📄 What’s a Makefile?
A Makefile is a file that lets you run Terraform commands like:
```sh
make init
make plan
make apply
```

Instead of remembering and typing full commands like:
```sh
terraform init
terraform plan
terraform apply
```


### 🚀 Why Use It?
Using make helps you:
- ✅ Run Terraform commands quickly and easily
- ✅ Keep commands consistent across the team
- ✅ Prepare for interviews or CI/CD automation


### 🛠 How to Use It
In your terminal, run:
```sh
make init      # Set up Terraform
make plan      # Preview changes
make apply     # Apply changes
make destroy   # Tear down resources (if needed)
```

You can also run:
```sh
make fmt       # Format .tf files
make validate  # Check for syntax errors
make clean     # Remove .terraform and state files (be careful!)
```

### 📁 Where’s the Makefile?
It’s located at [`terraform/Makefile`](./Makefile). Open it to see all available commands.

### 🗂️ Sample Terraform Project Structure with Makefile
Here’s a simple example of how your Terraform project directory might look:

```sh
terraform-project/
├── main.tf                  # Main Terraform config
├── Makefile                 # Automation file (init, plan, apply, etc.)
├── README.md                # Project documentation
```


### 🧠 Summary

| If your setup is...   | Do this                                                              |
| --------------------- | -------------------------------------------------------------------- |
| Simple project        | ✅ One Makefile in the root folder                                    |
| Multiple modules      | 📂 One Makefile in each module (optional)                            |
| Multiple environments | 🧩 Use folder-specific Makefiles or script logic in one central file |
