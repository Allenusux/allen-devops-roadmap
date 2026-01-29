# Allen DevOps Roadmap (Zero-to-Job Portfolio)

This repository is my learning roadmap and portfolio tracker as I transition into DevOps.  
Each phase has **clear deliverables**, **measurable acceptance criteria**, and **public proof** (code, docs, diagrams, screenshots, and demos) stored in dedicated GitHub repositories.

---

## Portfolio Structure (Repos)

1. **Phase 1 — Foundation & Reproducible Environment**
   - Repo: `devops-foundation`

2. **Phase 2 — Project 1: Containerised App on AWS EC2**
   - Repo: `project-1-containerized-app-on-ec2`

3. **Phase 3 — Core DevOps: CI/CD + Infrastructure as Code**
   - Repo: `iac-aws-ec2-vpc` + CI/CD inside Project 1 (or separate repo if needed)

4. **Phase 4 — Kubernetes + Observability + Interview-Ready Storytelling**
   - Repo: `project-2-k8s-deployment`

> Notes:
> - GitHub is the source of truth. Everything is reproducible from documentation.
> - Each repo includes: README, architecture diagram, runbook, troubleshooting, and evidence (screenshots/logs).

---

## Phase 1 (2–3 weeks): Foundation & Reproducible Environment

### Goal
Be able to provision a basic AWS environment and run a containerised service on EC2, with documentation that others can reproduce.

### Deliverables (Quantified)
- [ ] Create repo: `devops-foundation`
- [ ] **README.md** (>= 800 words) including:
  - prerequisites (local + AWS)
  - step-by-step commands
  - troubleshooting section (>= 5 items)
- [ ] AWS resources (minimum):
  - [ ] 1 x EC2 (Ubuntu)
  - [ ] 1 x Security Group (22/80)
  - [ ] 1 x IAM user/role (document least-privilege intention)
- [ ] Evidence:
  - [ ] `docs/` folder with >= 8 screenshots (EC2, SG, SSH, docker, browser access, etc.)

### Technologies Used
- Linux: `ssh`, permissions, system services, logs (`journalctl`)
- Git: clone/commit/push
- Docker: run/logs
- AWS: EC2, IAM, Security Groups

### Acceptance Criteria
- [ ] From a fresh machine, I can deploy **nginx on EC2** and access it via public IP in **<= 30 minutes**
- [ ] Another person can follow the README and reproduce the result without my help

---

## Phase 2 (3–5 weeks): Project 1 — Containerised App on AWS EC2

### Goal
Deliver an end-to-end “realistic” deployment: local → containerised → deployed → publicly accessible → repeatable update process.

### Deliverables (Quantified)
- [ ] Create repo: `project-1-containerized-app-on-ec2`
- [ ] Required repo files:
  - [ ] `Dockerfile`
  - [ ] `docker-compose.yml`
  - [ ] `scripts/deploy.sh` (one-click deployment script)
  - [ ] `README.md` (>= 1200 words)
- [ ] Optional but recommended:
  - [ ] `nginx.conf` (reverse proxy) and explain why it is used
- [ ] Documentation:
  - [ ] Architecture diagram: `docs/architecture.png`
  - [ ] Runbook: `docs/runbook.md` (start/stop/update/rollback basics)
  - [ ] Troubleshooting section in README (>= 8 items)
- [ ] Releases:
  - [ ] GitHub Releases >= 2 (e.g., `v0.1`, `v1.0`)
- [ ] Demo evidence:
  - [ ] 1 short demo video (2–5 mins) OR 1 GIF showing deployment steps

### Technologies Used
- Docker / Docker Compose
- Linux (service management, logs)
- Nginx (optional reverse proxy)
- AWS EC2
- GitHub Releases and documentation

### Acceptance Criteria
- [ ] `docker-compose up` runs the app locally from a fresh clone
- [ ] Remote deployment is repeatable using `scripts/deploy.sh`
- [ ] I can explain in 2 minutes: what I built, why, key issues, and how I fixed them

---

## Phase 3 (4–8 weeks): Core DevOps — CI/CD + Infrastructure as Code

### Goal
Automate delivery and make infrastructure reproducible via code.

### Deliverables (Quantified)
- [ ] CI/CD:
  - [ ] Add GitHub Actions workflow: `.github/workflows/ci-cd.yml`
  - [ ] At least 3 jobs:
    - [ ] lint/test (even basic checks)
    - [ ] build docker image
    - [ ] deploy (SSH to EC2 or pull from registry)
- [ ] Infrastructure as Code:
  - [ ] Create repo: `iac-aws-ec2-vpc`
  - [ ] Minimum Terraform resources:
    - [ ] VPC + Subnet + Route Table (basic networking)
    - [ ] Security Group
    - [ ] EC2 instance
  - [ ] Outputs:
    - [ ] `public_ip`
    - [ ] `ssh_command`
- [ ] Environments:
  - [ ] dev/prod separation using `tfvars` or workspaces
- [ ] Documentation:
  - [ ] `README.md` explaining `terraform init/plan/apply/destroy`
  - [ ] `docs/state-and-secrets.md` explaining how state/secrets are handled (even a simple approach)

### Technologies Used
- GitHub Actions
- Terraform (AWS provider)
- SSH-based deployments (scp/ssh)
- (Optional) Docker Hub / ECR

### Acceptance Criteria
- [ ] A push to `main` triggers build + deploy automatically (<= 10 minutes)
- [ ] `terraform destroy` cleanly removes resources (cost control)

---

## Phase 4 (ongoing): Kubernetes + Observability + Interview-Ready Storytelling

### Goal
Move from “can deploy” to “can operate”: Kubernetes basics, monitoring/logging, and incident-style troubleshooting.

### Deliverables (Quantified)
- [ ] Create repo: `project-2-k8s-deployment`
- [ ] Kubernetes manifests (minimum):
  - [ ] Deployment
  - [ ] Service
  - [ ] Ingress (or LoadBalancer equivalent)
  - [ ] ConfigMap + Secret (demo usage)
- [ ] Local cluster:
  - [ ] Use `kind` or `minikube` (EKS optional later)
- [ ] Observability:
  - [ ] Metrics: Prometheus + Grafana (or equivalent)
  - [ ] Logs: centralised view (lightweight setup acceptable)
- [ ] Incident simulation:
  - [ ] `docs/incident-sim.md` with 3 simulated failures and full troubleshooting notes:
    - [ ] CrashLoopBackOff
    - [ ] Port/networking issue
    - [ ] Resource limit / OOM / restarts
- [ ] Interview material:
  - [ ] 3 STAR stories (150–250 words each)
  - [ ] `docs/interview-qna.md` with >= 20 Q&A items

### Technologies Used
- Kubernetes (`kubectl`, manifests)
- (Optional) Helm
- Prometheus/Grafana (or equivalent)
- Troubleshooting (events/logs/describe)

### Acceptance Criteria
- [ ] I can demo: scale up/down, rollback, view dashboards, and identify a failure cause
- [ ] I have “incident-report style” documentation, not just notes

---

## How I Present My Work

### Primary: GitHub (Must)
- Pin the 4 repos to my GitHub profile
- Each repo front page shows:
  - architecture diagram
  - quick start
  - demo evidence
  - runbook and troubleshooting

### Optional: Lightweight Portfolio Page (Nice-to-have)
- GitHub Pages or Notion page with:
  - About (1 paragraph)
  - Projects (4 cards)
  - Resume link
  - Contact

---

## Progress Log (Weekly)

- Week 1:
  - [ ] Phase 1 EC2 + Docker + nginx + docs/screenshots
- Week 2:
  - [ ] Phase 2 app containerisation + deploy script + runbook
- Week 3–4:
  - [ ] CI/CD pipeline + Terraform VPC/EC2 module
- Week 5+:
  - [ ] Kubernetes + monitoring + incident simulations

---

## Contact
If you’re reviewing this portfolio and want a walkthrough, please open an issue in this repo and I’ll respond with a short demo video and explanation.
