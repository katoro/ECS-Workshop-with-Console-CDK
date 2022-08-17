# ECR Container Image 생성





```
ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)
REGION=$(aws configure get default.region)

echo "ACCOUNT_ID: $ACCOUNT_ID"
echo "REGION: $REGION"
sleep 1

docker build -t sample-rest-api .

docker tag sample-rest-api:latest ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com/my-ecr-repo:latest

aws ecr get-login-password --region ${REGION} | docker login --username AWS --password-stdin ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com

aws ecr create-repository --repository-name my-ecr-repo --image-scanning-configuration scanOnPush=true --region ${REGION}

docker push ${ACCOUNT_ID}.dkr.ecr.${REGION}.amazonaws.com/my-ecr-repo:latest
```
