# ECR Container Image 생성

## 개요

ECS에서 사용할 컨테이너 이미지를 만들어 봅니다. 만들어진 컨테이너 이미지는 ECR에 등록되어집니다.

## 실습

* Cloud9 콘솔을 실행한 다음, 아래 명령어를 수행해서 해당 경로로 이동합니다.

```
cd ~/environment/ecs-ec2-cdk/app
```

![](../.gitbook/assets/image.png)

* 아래 명령어를 수행합니다.&#x20;



```
ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)
REGION=$(aws configure get default.region)

echo "ACCOUNT_ID: $ACCOUNT_ID"
echo "REGION: $REGION"

docker build -t sample-rest-api .

docker tag sample-rest-api:latest ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com/my-ecr-repo:latest

aws ecr get-login-password --region ${REGION} | docker login --username AWS --password-stdin ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com

aws ecr create-repository --repository-name my-ecr-repo --image-scanning-configuration scanOnPush=true --region ${REGION}

docker push ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com/my-ecr-repo:latest
```
