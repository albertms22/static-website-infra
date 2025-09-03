# Terraform Static Website Infrastructure

This project provisions the infrastructure for hosting a **static website on AWS** using Terraform.  
It uses an **S3 bucket** for storage and can be extended to include **CloudFront** for CDN distribution.  

> ⚠️ Note: The `site/` folder is ignored in Git. To run this project, add your own static files (e.g., `index.html`) into a local `site/` directory before deployment.

---

## Features

- Infrastructure defined as **code** with Terraform
- **S3 bucket** configured for static website hosting
- Parameterized setup with `variables.tf` and `terraform.tfvars.example`
- Outputs key deployment values (e.g., bucket endpoint)
- Easily extendable to include **CloudFront**, **Route 53**, and SSL

---

## Prerequisites

- [Terraform](https://www.terraform.io/downloads) installed
- [AWS CLI](https://docs.aws.amazon.com/cli/) configured with valid credentials
- An AWS account with access to S3 (free tier is enough for testing)

---

## Usage

1. **Clone this repository**
   ```bash
   git clone https://github.com/your-username/terraform-static-website.git
   cd terraform-static-website
2. **Add your site files**
   - Create a local site/ folder with at least an index.html file
   ```bash
   <h1>Hello from Terraform!</h1>
3. **Initialize Terraform**
   ```bash
   terraform init
4. **Review variables**
   - Copy the example file and adjust as needed:
   ```bash
   cp terraform.tfvars.example terraform.tfvars
5. **Deploy the infrastructure**
   ```bash
   terraform apply
6. Access your site
   Once applied, Terraform will output the website endpoint. Example:
   ```bash
   http://my-demo-site.s3-website-us-east-1.amazonaws.com

## Cleanup

To avoid AWS charges, always destroy resources when done:

  - terraform destroy


## Project Structure
<pre> ```bash . ├── main.tf # Core infrastructure ├── variables.tf # Input variables ├── outputs.tf # Outputs for easy access ├── terraform.tfvars.example # Example variable configuration ├── site/ # Your static website files (ignored in Git) └── README.md # Documentation ``` </pre>


## Notes

This project is for educational and portfolio purposes.

It does not include production hardening (e.g., HTTPS with ACM, custom domain, WAF).

Extend it to demonstrate more advanced AWS + Terraform concepts.
