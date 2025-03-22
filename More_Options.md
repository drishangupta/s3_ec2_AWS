# AWS Website Deployment Options 🚀

| Deployment Method      | Difficulty  | Estimated Cost 💰 | Description |
|------------------------|------------|------------------|-------------|
| **Amazon S3 + CloudFront** | 🟢 Easy | 💲 Very Low | Host static websites (HTML, CSS, JS) with global CDN & caching. |
| **AWS Amplify**        | 🟢 Easy  | 💲 Low | Great for frontend apps (React, Vue, Angular) with backend support. |
| **EC2 + Apache/Nginx** | 🟠 Medium | 💲💲 Medium | Fully customizable VM for hosting dynamic websites. Requires management. |
| **Elastic Beanstalk**  | 🟠 Medium | 💲💲 Medium | Auto-deploys apps (Node.js, Python, Java, etc.) with managed scaling. |
| **Lightsail**          | 🟠 Medium | 💲 Fixed | VPS-like solution with predictable pricing and easy setup. |
| **ECS + Fargate**      | 🔴 Hard | 💲💲💲 High | Containerized deployment for microservices (Docker-based). |
| **Kubernetes (EKS)**   | 🔴 Hard | 💲💲💲💲 Very High | Managed Kubernetes for scalable containerized apps. |

### ✅ Best Choices:
- **For Static Sites** → S3 + CloudFront (cheapest & easiest)
- **For Web Apps** → AWS Amplify (serverless & managed)
- **For Full Control** → EC2 or Lightsail (manual setup)
