# IAM 생성

## 개요

ECS 실습을 위한 권한들을 설정합니다.

## 실습

* 서비스 검색창에 IAM을 검색한 뒤 IAM을 선택합니다.

![](<../.gitbook/assets/image (6).png>)

* 좌측 탭에서 역할을 선택한 뒤, 우측에 역할 만들기를 클릭합니다.

![](<../.gitbook/assets/image (14).png>)

* 사용자 지정 신뢰 정책을 선택한 뒤 아래 내용을 입력한 뒤, 다음 을 클릭합니다.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": "ecs-tasks.amazonaws.com"
            },
            "Action": "sts:AssumeRole"
        }
    ]
}
```

![](<../.gitbook/assets/image (7).png>)

* 권한 정책 검색창에서 AmazonECSTaskExecutionRolePolicy를 검색한 뒤 선택합니다.

![](<../.gitbook/assets/image (11).png>)

* 역할 이름에 AmazonECSTaskExecutionRole 을 입력하고 역할 생성을 클릭합니다.&#x20;

![](<../.gitbook/assets/image (34).png>)

* "AmazonECSTaskExecutionRole" 역할이 생성되었습니다.

![](<../.gitbook/assets/image (5).png>)

* 좌측 탭에서 역할을 선택한 뒤, 우측에 역할 만들기를 클릭합니다.

![](<../.gitbook/assets/image (14).png>)

* 사용자 지정 신뢰 정책을 선택한 뒤 아래 내용을 입력한 뒤, 다음 을 클릭합니다.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Service": "ecs-tasks.amazonaws.com"
            },
            "Action": "sts:AssumeRole"
        }
    ]
}
```

![](<../.gitbook/assets/image (7).png>)



* 권한 정책 검색창에서 AWSXrayWriteOnlyAccess, AmazonSSMReadOnlyAccess를 검색한 뒤 각각 선택합니다.

![](<../.gitbook/assets/image (19).png>)

![](<../.gitbook/assets/image (12).png>)

* 우측에 정책 생성 버튼을 클릭합니다.

![](<../.gitbook/assets/image (23).png>)

* JSON 탭을 클릭 후 아래 내용을 입력한 뒤 다음을 누릅니다. 태그 추가는 하지 않고, 다음:검토 까지 클릭합니다.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": [
                "ssmmessages:CreateControlChannel",
                "ssmmessages:CreateDataChannel",
                "ssmmessages:OpenControlChannel",
                "ssmmessages:OpenDataChannel"
            ],
            "Resource": "*",
            "Effect": "Allow"
        }
    ]
}
```

![](<../.gitbook/assets/image (27).png>)

* 정책의 이름은 ECSExec를 입력하고 정책을 생성합니다.

![](<../.gitbook/assets/image (9).png>)

* 다시 권한 추가화면으로 돌아와서, ECSExec를 검색하여 선택합니. 검색되지 않으면 새로고침 아이콘을 클릭한 뒤 다시 검색합니다.&#x20;

![](<../.gitbook/assets/image (4) (1).png>)

* 역할 이름은 ECSDefaultTaskRole로 입력한 뒤 역할 생성을 클릭합니다.

![](<../.gitbook/assets/image (26).png>)

* "ECSDefaultTaskRole" 역할이 생성되었습니다

![](<../.gitbook/assets/image (1) (1).png>)

## 결과

* 아래과 같이 두가지 역할이 생성되었습니다.
