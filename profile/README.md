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

xxxx를 목표로 xxxx했다.

### Demo Video (Youtube)

#### WAF Rule & Slack Alarm
![alt text](image.png)
[![WAF Rule & Slack Alarm Video](/assets/img/waf_rule_and_slack_alarm_thumbnail.png)](https://www.youtube.com/watch?v=S6AAgXVevEw)

#### HCP Terraform

[ Terraform destroy -> apply -> frontend, backend ci/cd -> web endpoint -> 로그인 영상 추가 ]

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
