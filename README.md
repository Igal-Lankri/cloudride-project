# Cloudride Challenge - Igal Lankri

Hi Shuki, Danit and Segev! This is my submission for the technical home assignment.
I've built a fully automated, containerized environment on AWS using Terraform and GitHub Actions.

## 🛠 What's in the box?

* **Infrastructure:** Terraform (managing VPC, ECS, ALB, ECR, etc.)
* **App:** A simple Nginx container serving a custom HTML page.
* **CI/CD:** GitHub Actions pipeline that builds and deploys on every push.

---

## 🏗 The Architecture

I designed the system to be secure by default but simple to manage.
* **Public Zone:** The Application Load Balancer (ALB) and NAT Gateway sit here to handle internet traffic.
* **Private Zone:** The application itself (ECS Fargate Tasks) runs here. It's completely isolated from the internet for security.

---

## ▶️ How to run it

1.  **Build the Infrastructure:**
    ```bash
    cd terraform
    terraform init
    terraform apply
    ```

2.  **Deploy the Code:**
    Just push a change to the `main` branch. GitHub Actions will handle the rest.

3.  **Check it out:**
    Grab the URL from the terraform output:
    ```bash
    terraform output alb_dns_name
    ```

Enjoy!
