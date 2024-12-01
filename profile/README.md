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

**HCP Terraform**을 **VCS(Version Control System)**와 연동하여 코드를 기반으로 AWS 리소스를 프로비저닝하고 관리

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
