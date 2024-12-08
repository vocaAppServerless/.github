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

> **⚠️ Note**: This repository is currently a demo version and is continuously being updated. Please refer to the [GitHub repository](https://github.com/nurdworker/rememberme) for the latest updates. 

### 🎬 Implementation Demo Video
  
### 💻Frontend Architecture
#### 🌐Global Data and Function Management
- **Redux**: Define global state in **store.ts**.
- **Static Data & Functions**: Manage static variables, functions, and class constructors in **staticData.ts**.
- **Redux State Access & Modification Functions**: Store general functions that require access to and modification of Redux state in the useFuncs.ts custom hook.
- **Queue Management**: Manage the queue using useContext in **QueueContext.tsx**.
- **Authentication Functions**: Modularize authentication logic in **auth.ts**.

### 💻Backend Architecture
#### 💾Lambda Caching and DB Connection Optimization
- **Cold Start and Warm Start Optimization**:
  - Store Secrets and DB connection data in global variables (cachedSecrets, cachedDb).
  - **Reuse the data** during the warm start to improve performance.
- **DB Connection Management**:
  - Create and reuse one DB connection **per Lambda container**.
  - tomatically generate the required number of connections based on Lambda's **auto-scaling**, maximizing resource efficiency.
#### ♻️Enhanced Code Reusability
  - **Lambda Templateization**:
    - **Handlers**: Separate the logic for each request into individual handlers for better management.
    - **Main Handler**: Include **middleware** and **caching logic** in the main handler to handle authentication and data caching efficiently.

### ⚙️Development/Production Environment Separation
**Frontend**
- **Development Environment**: Manage environment variables using **.env** and run local development with the **npm start**.
- **Production Environment**: Utilize **AWS S3** and **Parameter Store** for secure and reliable deployment.

**Backend**
- **Development Environment**:
  - Manage environment variables with **.env** and **env.json** files.
  - Use **Node.js** and **AWS SAM CLI** for local testing and development.
- **Production Environment**:
  - Secure sensitive information management with **AWS Secrets Manager**.
  - Optimize deployment using **Lambda Layers**.
 
### 🔑Auth Authentication and API Request Optimization
- The authentication method used is **Google OAuth**.
- **Reprocess existing requests** to enhance the user experience. 
  - **Frontend Authentication**:
    - Use **Axios interceptors** to handle token renewal logic.
  - **Backend Authentication**:
    - Use **middleware** on the backend to handle authentication requests centrally.




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
