---
description: 기
---

# CDK 준비하기

## 개요

CDK를 통해 ECS를 다뤄보기에 앞서, CDK 를 설치하고 사용을 준비합니다.

## 실습

* Cloud9 콘솔에서 아래 명령어를 수행합니다.

```
cd ~/environment/ecs-ec2-cdk/

npm install aws-cdk-lib

ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)
REGION=$(aws configure get default.region)

cdk bootstrap aws://${ACCOUNT_ID}/${REGION}
```

![](<../.gitbook/assets/image (4).png>)

{% hint style="info" %}
위의 명령어는 aws-cdk-lib 라이브러리를 설치 후 cdk 사용을 위해 계정정보를 기반으로 부트스트래핑 하는 명령어의 일련입니다.
{% endhint %}

