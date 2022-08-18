# ECS Service 생성

## 개요

ECS 실습을 위한 IAM을 만듭니다. VPC에 대해 더 자세한 사항이 알고 싶으면 [링크](https://docs.aws.amazon.com/ko\_kr/vpc/latest/userguide/what-is-amazon-vpc.html) 참고하세요.

## 실습

* Cloud9 콘솔에서 아래 명령어를 수행합니다.

```
cd ~/environment/ecs-ec2-cdk/ecs-restapi-service/
cdk deploy
```

* 아래와 같이 CDK에 의해서 CloudFormation 작업이 수행됩니다

![](<../.gitbook/assets/스크린샷 2022-08-18 오후 11.34.08.png>)

## 결과

* 아래와 같이 클러스터에 서비스가 동작하게 됩니다.

![](<../.gitbook/assets/스크린샷 2022-08-18 오후 11.37.17.png>)

* 서비스 이름을 클릭한 뒤 로드밸런서 항목을 클릭하여 DNS 이름으로 접속하면 결과 화면 (OK)를 볼 수 있다.

![](<../.gitbook/assets/스크린샷 2022-08-18 오후 11.40.49.png>)

{% hint style="info" %}
접속이 되지 않을시에는 로드밸런서 보안그룹 정책을 확인해봅니다.
{% endhint %}
