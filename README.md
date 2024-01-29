# Account Project
<img src="https://img.shields.io/badge/springboot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white">  <img src="https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=Gradle&logoColor=white">  <img src="https://img.shields.io/badge/java-%23ED8B00?style=for-the-badge&logo=openjdk&logoColor=white"> 
<br/><br/>

## 📜프로젝트 소개
- Spring boot와 Java를 활용하여 Account(계좌 관리) 시스템을 만드는 프로젝트

- 계좌 추가/해지/확인, 거래 생성/거래 취소/거래 확인의 6가지 API를 제공
<br/><br/>
## ⏱개발 기간
* 2024.01.19 ~ 2024.01.29
<br/><br/>

## ⭐주요 기능

### 💵 계좌 관련 API<br/><br/>
**1. 계좌 생성** <br/><br/>
&ensp; - 성공: 사용자 아이디, 생성된 계좌 번호, 등록일시(LocalDateTime) 응답<br/><br/>
&ensp; - 실패 : 사용자 없는 경우, 계좌가 10개(사용자당 최대 보유 가능 계좌) 인 경우 실패 응답

**2. 계좌 해지** <br/><br/>
&ensp; - 성공: 사용자 아이디, 계좌번호, 해지일시 응답<br/><br/>
&ensp; - 실패 : 사용자 없는 경우, 사용자 아이디와 계좌 소유주가 다른 경우, 계좌가 이미 해지 상태인 경우, 잔액이 있는 경우 실패 응답

**3. 계좌 확인** <br/><br/>
&ensp; - 성공: (계좌번호, 잔액) 정보를 Json list 형식으로 응답<br/><br/>
&ensp; - 실패 : 사용자 없는 경우 실패 응답


### 💵 거래(Transaction) 관련 API<br/><br/>
**1. 잔액 사용** <br/><br/>
&ensp; - 성공: 계좌번호, transaction_result, transaction_id, 거래금액, 거래일시 응답<br/><br/>
&ensp; - 실패 : 사용자 없는 경우, 사용자 아이디와 계좌 소유주가 다른 경우, 계좌가 이미 해지 상태인 경우, 거래금액이 잔액보다 큰 경우, 거래금액이 너무 작거나 큰 경우 실패 응답

**2. 잔액 사용 취소** <br/><br/>
&ensp; - 성공: 계좌번호, transaction_result, transaction_id, 취소 거래금액, 거래일시 응답<br/><br/>
&ensp; - 실패 : 원거래 금액과 취소 금액이 다른 경우, 트랜잭션이 해당 계좌의 거래가 아닌경우 실패 응답

**3. 거래 확인** <br/><br/>
&ensp; - 성공: 계좌번호, 거래종류(잔액 사용, 잔액 사용 취소), transaction_result, transaction_id, 거래금액, 거래일시 응답<br/><br/>
&ensp; - 실패 : 해당 transaction_id 없는 경우 실패 응답




