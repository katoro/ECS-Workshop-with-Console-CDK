# ECR Container Image 생성

## 개요

ECS에서 사용할 컨테이너 이미지를 만들어 봅니다. 만들어진 컨테이너 이미지는 ECR에 등록되어집니다.

## 실습

* Cloud9 콘솔을 실행한 다음, 아래 명령어를 수행해서 해당 경로로 이동합니다.

```
cd ~/environment/ecs-ec2-cdk/app
```

![](<../.gitbook/assets/image (4) (2).png>)

* 아래 명령어를 수행합니다.&#x20;

<pre><code>ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)
REGION=$(aws configure get default.region)

echo "ACCOUNT_ID: $ACCOUNT_ID"
echo "REGION: $REGION"

docker build -t sample-rest-api .
<strong>
</strong>docker tag sample-rest-api:latest ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com/my-ecr-repo:latest

aws ecr get-login-password --region ${REGION} | docker login --username AWS --password-stdin ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com

aws ecr create-repository --repository-name my-ecr-repo --image-scanning-configuration scanOnPush=true --region ${REGION}

docker push ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com/my-ecr-repo:latest</code></pre>

{% hint style="info" %}
Account와 Region 관련된 정보를 정한 다음, 도커 이미지를 빌드합니다. 이후 ECR 리포지토리를 생성한 뒤, 빌드된 이미지를 push하여 ECR 리포지토리에 올려두는 명령어들입니다.
{% endhint %}

* 아래 화면과 같이 빌드및 리포지토리 생성, 업로드가 완료됩니다.

![](<../.gitbook/assets/image (28).png>)

## 결과

* 서비스 검색창에 elastic container registry를 검색한 뒤 선택합니다.

![](<../.gitbook/assets/image (6).png>)

* 아래와 같은 이미지가 보여집니다.

![](<../.gitbook/assets/image (5).png>)
