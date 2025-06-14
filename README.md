<div align="center">
    <img src="./images/coderco.jpg" alt="CoderCo" width="300"/>
</div>

# 🚀 BYO App/Service on GCP Cloud Run or Cloud Functions — You Decide!

You’ll design and build a small app or service — anything you like — then deploy it to GCP using Terraform. The only non-negotiable requirements are below. Everything else is up to you.

## Requirements 📝

### Create Your Own App/Service

- Must have at least one route or endpoint serving dynamic data (e.g., JSON, HTML, or custom output).
- You decide the tech stack, language, framework, etc.
- README must include minimal instructions for local setup (e.g., npm install && npm start, etc.).

### Deployment Target: Cloud Run or Cloud Functions (you pick)

- If you choose Cloud Run, containerize your app using Docker and deploy it. Push image to Artifact Registry or Docker Hub.
- If you choose Cloud Functions, package your function for deployment.
- Code must be version-controlled (e.g., GitHub, GitLab, etc.).
- Must run behind HTTPS — use a custom domain with HTTPS via Cloud Load Balancing + SSL cert or Cloud Run domain mappings + managed certs.

### Terraform: Infrastructure as Code

- Use Terraform for all infrastructure, including:
  - Cloud Run / Cloud Functions
  - Artifact Registry or GCS bucket
  - DNS (Cloud DNS)
  - SSL Certificates (Managed SSL Certs)
  - Load Balancer or domain mappings
- Structure your Terraform cleanly — no all-in-one main.tf.
- Demonstrate best practices: input variables, output modules, DRY patterns.

### CI/CD Pipeline

- Must include an automated pipeline to:
  - Build and test the app
  - Deploy to GCP (either Cloud Run or Functions)
- Use GitHub Actions or any other CI/CD platform (GitLab CI, CircleCI, etc. Bonus points: Jenkins 💀).
- No secrets in code:
  - Use Secret Manager, encrypted Terraform vars, or another secure method.
  - Bonus: use self-hosted Vault for secrets.

### Architecture Diagram

- Must clearly show how your infra and app components fit together.
- Use draw.io, Lucidchart, Mermaid, or even ASCII art.
- Add this to your README.md.

### Project Deliverables

- Git repo with:
  - App code (backend/API/function code)
  - Terraform code (clean structure)
  - Pipeline code (.github/workflows/* or equivalent)
- Live service deployed to https://<app>.<your-domain> or https://<whatever>.labs.<your-domain>
- README including:
  - Setup instructions
  - Screenshots of the running app
  - Architecture diagram
  - Explanation or link to the CI/CD pipeline

### Constraints & Hints (No Hand-holding)

- Security: Use IAM roles, not hardcoded keys. Rotate secrets properly.
- Terraform: You can use modules/providers from the registry but must demonstrate correct integration and understanding.
- HTTPS/Domain: No plain HTTP. Use domain verification, SSL certs (managed), DNS records via Cloud DNS.
- Advanced Bonus:
  - Canary deployments (e.g., Cloud Run revisions with traffic splitting)
  - Multiple environments (staging/prod)
  - Logging/monitoring setup with Cloud Logging, Error Reporting, or OpenTelemetry

### GCP Equivalents (AWS to GCP)

| AWS | GCP  Equivalent |
| --- | --- |
| ECS Fargate | Cloud Run |
| Lambda | Cloud Functions |
| ECR | Artifact Registry |
| ACM | Managed SSL Certs |
| Route 53 | Cloud DNS |
| Application LB | Cloud Load Balancer
| Secrets Manager | Secret Manager
| IAM Roles/Policies | GCP IAM
| CodePipeline | Cloud Build or any CI
