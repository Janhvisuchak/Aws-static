# Static Website Hosting on AWS with Terraform

This project sets up a static website hosting solution on AWS using Terraform. The infrastructure leverages AWS Route 53, CloudFront, S3, Certificate Manager, and a CloudFront Function to provide a highly available, scalable, and secure environment for hosting static content.

## Architecture Overview
### Components:
- **Client**: End-user accessing the website.
- **Route 53**: AWS's Domain Name System (DNS) service to resolve DNS queries and route traffic to the website.
- **Certificate Manager**: Manages SSL/TLS certificates for securing HTTPS communication.
- **CloudFront Distribution**: Content Delivery Network (CDN) that serves cached or original content from the S3 bucket.
- **CloudFront OAC + S3 Bucket Policy**: Ensures secure access to the S3 bucket, allowing only authorized CloudFront distributions.
- **CloudFront Function**: Handles HTTP redirects for domain consistency and routing.
- **Private S3 Bucket**: Stores the static website files with restricted direct public access.
- **Static Web Files**: HTML, CSS, and JavaScript files that make up the website content.

## Getting Started

### Prerequisites:
- **Terraform**: Ensure Terraform is installed on your local machine.
- **AWS CLI**: Configure the AWS CLI with the appropriate credentials.

### Configuring Variables:
Terraform uses variables to manage settings in a flexible manner. To set up your environment:

1. **Create a Variables File**:
   - Create a file named `terraform.tfvars` in the project root.
   - This file will store the values for variables defined in `variables.tf`.

   **Example `terraform.tfvars` content:**
   ```hcl
   aws_region  = "us-west-2"
   prefix      = "your-org-prefix"
   domain_name = "yourdomain.com"
   bucket_name = "website-name-frontend"
   common_tags = {
     ManagedBy = "Terraform"
     Org       = "Your Organization Name"
     Project   = "Static Website"
   }
   ```

### Deploying to AWS:
1. **Initialize Terraform**:
   ```bash
   terraform init
   ```

2. **Generate an Execution Plan**:
   ```bash
   terraform plan
   ```

3. **Apply the Configuration**:
   ```bash
   terraform apply
   ```

### Cleanup:
To remove the provisioned infrastructure and avoid ongoing charges, use:

```bash
terraform destroy
```

## Further Reading
For a deeper understanding of how to set up and master static website hosting on AWS with Terraform, read this tutorial:

**[Mastering Static Website Hosting on AWS with Terraform: A Step-by-Step Guide](#)**

## Thank You
Thank you for taking the time to explore this project. Your interest and feedback are highly valued!

## Contribution
Contributions are welcome! Whether it's reporting bugs, suggesting enhancements, or contributing code, your input is always appreciated. Feel free to open an issue or submit a pull request.

--- 
