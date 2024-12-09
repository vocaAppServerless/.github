# Remember Me

Lambda 기반 서버리스 단어 암기 웹사이트

## Tech Stack

- Frontend   : React
- Backend:   : Node.js, AWS SAM CLI
- Database   : MongoDB
- CI/CD      : GitHub Actions
- Cloud(AWS) : Lambda, API Gateway, S3, CloudFront, Route53, WAF, Parameter Store, Secrets Manager, Budgets, Chatbot
- IaC        : Terraform(HCP Terraform)
- Logging    : CloudWatch, Logstash, Elasticsearch, Kibana
- ETC        : Git/GitHub, Slack, Notion

## Development

> **⚠️ Note**: This repository is currently a demo version and is continuously being updated. Please refer to the [GitHub repository](https://github.com/nurdworker/rememberme) for the latest updates. 

### 🎬 Implementation Demo Video: 
- <https://youtu.be/y15djTDnXYg>
  
### **Frontent Dev Environment**
#### React Project Setup and Running Guide
1. **Clone our project repository**
```bash
git clone https://github.com/vocaAppServerless/frontend.git
```
2. **Install Dependencies and run**
Before starting the React project, you need to install the required dependencies. Run the following command:
```bash
npm install
```
3. **Start the Application**
```bash
npm start
```

### **Backend**
1. **Clone our project repository**
```bash
git clone https://github.com/vocaAppServerless/backend.git
```
2. **Install AWS SAM CLI**
- Windows
  - Download the installer from the [AWS SAM CLI Download Page](https://aws.amazon.com/serverless/sam/).
  -  Run the installer and follow the on-screen instructions.
  - Add the installation path (usually `C:\Program Files\Amazon\AWSSAMCLI\bin`) to your `PATH` environment variable if not automatically configured.
- macOS
  - Install using Homebrew:
   ```bash
   brew install aws/tap/aws-sam-cli
   ```
3. **Build and Test API Gateway with Lambda**
To build the API Gateway and Lambda environment using SAM, run:
```bash
sam build --no-cached
sam local start-api --env-vars ./env.json --no-cached
```
**env.json for SAM CLI**
```json
{
  "<lambda-name-1>": {
    "ENV_FIRST": "...",
    "ENV_SECOND": "///"
  },
  "<lambda-name-2>": {
    "ENV_FIRST": "...",
    "ENV_SECOND": "///"
  }
}
```
The added warning ensures users understand that **environment variables** are **crucial** for the proper functioning of Lambda functions and must be specified correctly in the `env.json` file.




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
