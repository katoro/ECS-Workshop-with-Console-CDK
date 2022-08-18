# ECS Cluster 생성

## 개요

ECS 클러스터는 태스크 혹은 서비스를 관리하는 논리적 그룹입니다

## 실습

* 서비스 검창에 ECS를 검색한  Elastic Container Service를 선택합니다.

![](<../.gitbook/assets/image (28) (1).png>)

* 좌측 메뉴의 클러스터를 선택한 다음, 우측의 클러스터 생성 버튼을 클릭합니다.&#x20;

![](<../.gitbook/assets/image (8).png>)

{% hint style="info" %}
콘솔의 화면이 위 다른 경우 새로운 ECS환경 토글 버튼을 클릭하면 됩니다.
{% endhint %}

* 네트워킹 설정입니다. 클러스터 이름은 manual-ecs-ec2, VPC는 앞선 실습에서 만든 ecs-manual-vpc를 선택합니다. 서브넷은 **퍼블릭** 서브넷 3개를 선택합니다.

![](<../.gitbook/assets/image (13) (1).png>)

* 인프라 설정입니다. Amazon EC2 인스턴스를 선택합니다. 새 ASG 생성을 고른 다음 운영체제는 Amazon Linux 2, EC2 인스턴스 유형은 c5.xlarge, 용량은 최소1/최대10을 선택합니다.

![](<../.gitbook/assets/image (22).png>)

* 모니터링 설정입니다. Conatiner Insights 사용 토글을 ON 해줍니다.

![](<../.gitbook/assets/image (29).png>)

* 나머지 설정은 변경하지 않고, 생성 버튼을 누르면 생성이 진행됩니다.

![](<../.gitbook/assets/image (2) (2).png>)

## 결과

* 다음과 같이 클러스터가 생성되었습니다.

![](<../.gitbook/assets/image (18).png>)
