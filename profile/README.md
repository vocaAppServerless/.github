# Remember Me

Lambda 기반 서버리스 단어 암기 웹사이트

## Tech Stack

- Frontend   :
- Backend:   :
- Database   : MongoDB
- CI/CD      : GitHub Actions
- Cloud(AWS) : Lambda, API Gateway, S3, CloudFront, Route53, WAF, Parameter Store, Secrets Manager, Budgets, Chatbot
- IaC        : Terraform(HCP Terraform)
- Logging    : CloudWatch, Logstash, Elasticsearch, Kibana
- ETC        : Git/GitHub, Slack, Notion

## Infra

[ Terraform destroy -> apply -> frontend, backend ci/cd -> web endpoint -> 로그인 영상 추가 ]

### Architecture

![Architecture](/assets/img/architecture.png)

### CI/CD Workflow - [Backend]

![Backend CI/CD](/assets/img/backend_ci_cd.png)

### CI/CD Workflow - [Frontend]

![Frontend CI/CD](/assets/img/frontend_ci_cd.png)

### Logging Workflow

![Logging Workflow](/assets/img/log_monitoring.png)

![Kibana Dashboard](/assets/img/kibana_dashboard.png)
