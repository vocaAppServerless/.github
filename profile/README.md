# Remember Me

Lambda 기반 서버리스 단어 암기 웹사이트

## Tech Stack

- Frontend   : React
- Backend:   : Node.js, AWS Lambda, AWS SAM CLI
- Database   : MongoDB
- CI/CD      : GitHub Actions
- Cloud(AWS) : Lambda, API Gateway, S3, CloudFront, Route53, WAF, Parameter Store, Secrets Manager, Budgets, Chatbot
- IaC        : Terraform(HCP Terraform)
- Logging    : CloudWatch, Logstash, Elasticsearch, Kibana
- ETC        : Git/GitHub, Slack, Notion

## Development

### Development/Production Environment Separation
**Frontend 💻**
- **Development Environment**: Manage environment variables using **.env** and run local development with the **npm start** command.
- **Production Environment**: Utilize **AWS S3** and **Parameter Store** for secure and reliable deployment.

**Backend 🌐**
- **Development Environment**:
  - Manage environment variables with **.env** and **env.json** files.
  - Use **Node.js** and **AWS SAM CLI** for local testing and development.
- Production Environment:
  - Secure sensitive information management with **AWS Secrets Manager**.
  - Optimize deployment using **Lambda Layers**.

### Auth Authentication and API Request Optimization
- **Google OAuth Authentication Logic**:
  - Use Axios interceptors to handle token renewal logic.
  - Reprocess existing requests to enhance the user experience.
- **User Authentication Functions**:
  - Centralize user authentication functions in the **auth.ts** file.
 
### Lambda Caching and DB Connection Optimization
- **Cold Start and Warm Start Optimization**:
  - Store Secrets and DB connection data in global variables (cachedSecrets, cachedDb).
  - Reuse the data during the warm start to improve performance.
- **DB Connection Management**:
  - Create and reuse one DB connection per Lambda container.
  - tomatically generate the required number of connections based on Lambda's auto-scaling, maximizing resource efficiency.

### Enhanced Code Reusability
- **Lambda Templateization**:
  - **Handlers**: Separate the logic for each request into individual handlers for better management.
  - **Middleware**: Centralize the handling of all authentication requests through an authentication middleware.

## Infra

**HCP Terraform**을 **VCS**(Version Control System)와 연동하여 코드를 기반으로 AWS 리소스를 프로비저닝하고 관리

### Demo

**WAF Rule & Slack Alarm Demo** - <https://youtu.be/S6AAgXVevEw?si=OiLR3wfE36uTpHYU>

**HCP Terraform Demo** - <https://youtu.be/zg9rhHcf8w0?si=A6rGs7k0rcp9nD0u>

### Architecture

![Architecture](/assets/img/architecture.png)

### CI/CD - [Backend]

![Backend CI/CD](/assets/img/backend_ci_cd.png)

### CI/CD - [Frontend]

![Frontend CI/CD](/assets/img/frontend_ci_cd.png)

### Logging

- CloudWatch logs의 Subscription Filter를 사용해 ELK 클러스터로 로그 데이터 전송
- Kibana 대시보드를 사용해 log group별, status별 로그 확인 가능

![Logging Workflow](/assets/img/log_monitoring.png)

![Kibana Dashboard](/assets/img/kibana_dashboard.png)
