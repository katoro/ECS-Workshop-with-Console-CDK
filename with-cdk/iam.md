# IAM 생성

## 개요

ECS 실습을 위한 IAMd을 만듭니다. VPC에 대해 더 자세한 사항이 알고 싶으면 [링크](https://docs.aws.amazon.com/ko\_kr/vpc/latest/userguide/what-is-amazon-vpc.html) 참고하세요.

## 실습

* Cloud9 콘솔에서 아래 명령어를 수행합니다.

```
cd ~/environment/ecs-ec2-cdk/ecs-iam-role/
cdk deploy
```

* 아래와 같이 CDK에 의해서 CloudFormation 작업이 수행됩니다.

![](<../.gitbook/assets/image (15).png>)

## 결과

* 아래와 같이 IAM 역할이 생성됩니다.

![](<../.gitbook/assets/image (2).png>)