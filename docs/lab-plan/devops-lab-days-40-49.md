# DevOps Lab — Days 40–49

Phase: Terraform Deep Infrastructure

This phase introduces **Infrastructure as Code (IaC)** using Terraform.

Goals:

* Install Terraform
* Understand Terraform lifecycle
* Create infrastructure resources
* Manage Terraform state
* Implement modules
* Detect infrastructure drift
* Debug Terraform plans
* Simulate infrastructure failures
* Implement remote state
* Analyze Terraform graphs

All commands must be executed from **repository root** unless explicitly specified.

---

# DAY 40 — Terraform Installation and Environment

Type manually:

```
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
terraform version
terraform -help
terraform -help plan
terraform -help apply
terraform -help init
terraform -help validate
terraform -help fmt
terraform -help graph
terraform -help state
terraform -help workspace
terraform -help providers
terraform -help destroy
terraform -help output
terraform -help console
terraform -help show
terraform -help login
```

Create terraform lab folder.

```
mkdir -p terraform-lab/day40
cd terraform-lab/day40
terraform version
terraform -help
pwd
ls -la
```

Create first configuration.

```
touch main.tf
touch variables.tf
touch outputs.tf
touch provider.tf
```

Inspect files.

```
ls
cat main.tf
cat variables.tf
cat outputs.tf
```

---

# DAY 41 — First Terraform Resource

Navigate to working directory.

```
cd terraform-lab/day40
```

Edit provider.

```
nano provider.tf
```

Example provider configuration.

```
terraform {
 required_providers {
  local = {
   source = "hashicorp/local"
   version = "~> 2.4"
  }
 }
}
```

Initialize Terraform.

```
terraform init
terraform version
terraform providers
terraform providers mirror ./providers
```

Create resource.

```
nano main.tf
```

Example local file resource.

```
resource "local_file" "example" {
 filename = "hello.txt"
 content  = "Hello Terraform Lab"
}
```

Run Terraform lifecycle.

```
terraform fmt
terraform validate
terraform plan
terraform apply
```

Confirm resource.

```
ls
cat hello.txt
terraform state list
terraform state show local_file.example
```

---

# DAY 42 — Terraform State Inspection

Inspect Terraform state.

```
terraform state list
terraform state show local_file.example
terraform state pull
terraform state push terraform.tfstate
terraform show
terraform show terraform.tfstate
```

Analyze state JSON.

```
terraform show -json > state.json
cat state.json
```

Backup state.

```
cp terraform.tfstate terraform.tfstate.backup
ls
```

Remove state resource.

```
terraform state rm local_file.example
terraform plan
terraform apply
```

Recreate resource.

```
terraform apply
terraform state list
```

---

# DAY 43 — Terraform Variables

Create variables.

```
nano variables.tf
```

Example variable.

```
variable "file_content" {
 type = string
 default = "DevOps Lab Terraform"
}
```

Modify resource.

```
nano main.tf
```

Update resource.

```
content = var.file_content
```

Run Terraform commands.

```
terraform fmt
terraform validate
terraform plan
terraform apply
```

Override variable.

```
terraform apply -var="file_content=NewContent"
```

Verify result.

```
cat hello.txt
```

---

# DAY 44 — Terraform Outputs

Create outputs.

```
nano outputs.tf
```

Example output.

```
output "file_path" {
 value = local_file.example.filename
}
```

Run Terraform.

```
terraform fmt
terraform validate
terraform plan
terraform apply
terraform output
terraform output file_path
```

Inspect output JSON.

```
terraform output -json
```

Save outputs.

```
terraform output > outputs.txt
cat outputs.txt
```

---

# DAY 45 — Terraform Modules

Create modules directory.

```
mkdir -p modules/file
cd modules/file
```

Create module files.

```
touch main.tf
touch variables.tf
touch outputs.tf
```

Define module resource.

```
nano main.tf
```

Return to root module.

```
cd ../../
nano main.tf
```

Call module.

```
module "file_module" {
 source = "./modules/file"
}
```

Run Terraform.

```
terraform fmt
terraform init
terraform validate
terraform plan
terraform apply
```

Inspect state.

```
terraform state list
terraform state show module.file_module.local_file.example
```

---

# DAY 46 — Terraform Graph Analysis

Generate Terraform graph.

```
terraform graph
terraform graph > graph.dot
```

Install graphviz.

```
brew install graphviz
```

Render graph.

```
dot -Tpng graph.dot -o graph.png
open graph.png
```

Analyze dependencies.

```
terraform providers
terraform show
terraform state list
```

---

# DAY 47 — Terraform Drift Detection

Simulate drift.

Manually edit file.

```
nano hello.txt
```

Write new content.

Check drift.

```
terraform plan
terraform apply
```

Inspect changes.

```
terraform show
terraform state list
terraform state show local_file.example
```

---

# DAY 48 — Terraform Workspaces

List workspaces.

```
terraform workspace list
```

Create workspace.

```
terraform workspace new dev
terraform workspace new staging
terraform workspace new prod
```

Switch workspace.

```
terraform workspace select dev
terraform workspace select staging
terraform workspace select prod
```

Verify states.

```
terraform state list
terraform workspace show
```

---

# DAY 49 — Terraform Destroy and Recovery

Destroy infrastructure.

```
terraform plan -destroy
terraform destroy
```

Verify removal.

```
ls
terraform state list
```

Recreate infrastructure.

```
terraform apply
```

Inspect infrastructure.

```
terraform show
terraform state list
terraform output
```

Create final documentation.

```
mkdir -p docs
touch docs/terraform-lab.md
```

Document:

* Terraform lifecycle
* State management
* Modules
* Drift detection
* Workspaces
* Graph analysis
