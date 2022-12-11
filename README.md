# :sunny: Terraform-Study-1st

과거에는 모든 인프라를 수동으로 배포했어요  


이 시기는 어둠과 공포의 시기였어요
- 서버가 내려간다면?
- 구성을 잘못했다면?
- 배포가 느리고 잘 깨진다면?
- 인프라 관리자가 어둠의 저편으로 사라진다면? (i.e. 휴가)

그러나 시간이 지나고 DevOps라는 개념이 퍼지게 되면서 이러한 어둠과 공포의 시기를 이겨낼 수 있는 도구가 탄생했어요  

바로 Terraform 이에요  

Terraform은 HashiCorp에서 개발한 선언형 언어로 작성할 수 있는 IaC 오픈소스 도구에요  

### example
```terraform
provider "aws" {
  region = "us-east-2"
}

resource "aws_instance" "example" {
  ami           = "ami-0fb653ca2d3203ac1"
  instance_type = "t2.micro"
}
```
```shell
$ terraform init
$ terraform apply
```

이번 스터디에서는 Terraform의 기초를 다지고 활용할 수 있는 능력을 길러요

# :ok_man: 목표인 것
- IaC를 지향해야 하는 이유 알기
- Terraform이 무엇인지 알기
- Terraform을 왜 사용해야 하는지 알기
- Terraform을 언제 사용해야 하는지 알기
- Terraform 사용하는 방법 알기
- Terraform이 어떻게 동작하는지 알기
- 재사용 가능한 Terraform 코드 작성하는 법 알기
- 크리스마스가 오기 전 스터디 마무리하기

# :no_good_man: 목표가 아닌 것
- Terraform 코드 까보기
- Terraform 고수되기  
- 인프라 고수되기
- GCP, AZURE, NCP에 인프라 구성해보기
- Terraform Up & Running 5챕터 이후 내용 다루기

# :point_right: 대상
- 현직자
  - 시스템 관리자
  - 운영 엔지니어
  - 배포 엔지니어
  - 데이터 엔지니어
  - 사이트 신뢰성 엔지니어
  - DevOps 엔지니어
  - 인프라 관리자
  - 풀스택 개발자
  - CTO
  - 코드를 작성할 줄 알지만 운영은 잘 모르는 개발자
  - 운영은 잘 알지만 코드는 잘 작성하지 못하는 인프라 엔지니어
  - 이직 준비생
- 취준생
- 대학생
- 위 모든 내용에 해당되지 않지만 Terraform이 궁금한 사람

# :gear: 준비물
- Terraform Up & Running 책 (2판 이상)
  - Terraform Up & Running 3판이 22년도에 출판됐어요
  - 책의 1/3 이상이 변경될 정도로 많은 변화가 있지만 대부분 5챕터 이후의 내용들이라서 이번 스터디에서는 2판 이상이면 충분할 것 같아요
  - 혹시나 다른 내용이 있더라도 스터디 인원들과 맞춰보면서 진행하면 문제 없다고 생각해요 👍
- AWS 계정
- 컴퓨터

# :key: 방식
## :alarm_clock: 시간
매주 일요일 오후 9시에 온라인으로 진행해요
- 지각비나 보증금을 받지 않아요.
- 상호 신뢰를 기반으로 열심히 진행해요 :muscle:  


## :tokyo_tower: 장소
- Google meet에서 온라인으로 진행해요
  - [재영](https://github.com/heartcored98)님이 캘린더로 초대 주실 예정이에요
  - [Week 0](https://github.com/wjrmffldrhrl/Terraform-Study-1st/issues/3)에 이메일을 코멘트로 남겨주세요
- 스터디 4회차가 모두 끝나면 점심 or 저녁을 함께 해보려고 해요
  - 필수는 아니에요 😄

## :eyes: 진행 방법
- [Terraform Up & Running](https://www.oreilly.com/library/view/terraform-up-and/9781098116736/?_gl=1*1eaphy7*_ga*NjI5MDc0ODg3LjE2Njg4NDIxMTI.*_ga_092EL089CH*MTY2ODg0MjExMS4xLjEuMTY2ODg0MjE0My4yOC4wLjA.)을 일주일동안 읽어요
- 각자 읽은 내용을 바탕으로 정리해봐요
  - 다른 사람에게 설명하기 용이한 형태로 정리해요
  - 책에 나온 내용 이외에 얻게된 정보가 있으면 정리 내용에 포함해요
  - 어려웠던 내용이나 궁금했던 내용을 찾아서 정리 내용에 포함하거나 질문을 준비해요
  - 정리한 내용은 해당 repo에 [PR](https://github.com/wjrmffldrhrl/Terraform-Study-1st/pulls)로 공유해주세요
    - fork repository -> new branch -> commit -> pull requests
- 스터디가 시작되면 인원들 중 랜덤하게 한 명(분량에 따라 두 명 이상)을 뽑아서 발표를 진행해요
- 발표를 진행하면서 자유롭게 질문도 받아요
- 발표가 끝나고 자유롭게 서로 의견이나 질문을 나눠요
  - 발표자가 진행해주셔도 좋아요
- 실습하면서 어려움이 생기거나 궁금한점이 생겼는데 바로 해결하고 싶을 때는 해당 레포의 [issue](https://github.com/wjrmffldrhrl/Terraform-Study-1st/issues)에 올려주세요  


# :1234: 인원
- [조승현](https://github.com/wjrmffldrhrl)
- [김건우](https://github.com/kgw7401)
- [송지원](https://github.com/JionisGenius)
- [조재영](https://github.com/heartcored98)
- [이힘찬](https://github.com/ssilb4)
- [허준혁](https://github.com/JamesHeo)
- [이은빈](https://github.com/teno4944)
- [염경현](https://github.com/Gyeong-Hyeon)
- [바삭한다리](https://github.com/0805004949)

# :calendar: 주간 계획
|주차|날짜|챕터|발표자|
|:---:|:---:|---|:---:|
|0주차|11/20|Planning|[조승현](https://github.com/wjrmffldrhrl)|
|1주차|11/27|Why Terraform|[조승현](https://github.com/wjrmffldrhrl)|
|2주차|12/4|Getting Started With Terraform|[이은빈](https://github.com/teno4944), [조재영](https://github.com/heartcored98)|
|3주차|12/11|How To Manage Terraform State||
|4주차|12/18|How To Create Reusable Infrastructure With Terraform Modules||  

# :door: 참여 방법
아래 방법중 하나로 성함과 깃허브 아이디를 전달해주세요~!
- [Terraform study 1st에 오신것을 환영합니다!](https://github.com/wjrmffldrhrl/Terraform-Study-1st/issues/1) issue에 코멘트 남기기
- wjrmffldrhrl@gmail.com 으로 이메일 보내기
