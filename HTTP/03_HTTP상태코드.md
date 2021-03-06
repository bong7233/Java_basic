# 상태코드

클라이언트가 보낸 요청의 처리 상태를 응답에서 알려주는 기능  
- 1xx (Informational): 요청이 수신되어 처리중(거의 쓰지 X)
- 2xx (Successful): 요청 정상 처리
- 3xx (Redirection): 요청을 완료하려면 추가 행동이 필요
- 4xx (Client Error): 클라이언트 오류, 잘못된 문법등으로 서버가 요청을 수행할 수 없음
- 5xx (Server Error): 서버 오류, 서버가 정상 요청을 처리하지 못함

<br>

## 2XX - 성공
- 200 : ok
  - 응답을 잘 처리한경우
- 201 : Created
  - 서버에서 신규 리소스를 생성해서 붙인 경우
  - Location 정보도 포함하여 반환
- 202 : Accepted
  - 요청이 접수는 되었지만 처리되진 않음
  - 시간차로 요청이 처리되야하는 경우 사용
- 204 : No Content
  - 보통 서버의 응답 body에 반환할 데이터가 있어야하는데 없음
  - 주로 save기능 실행시 별다른 리턴이 없어도 될때 사용

<br>

## 3XX - 리다이렉션
요청 완료를위해 클라의 추가적인 과정이 필요함  
리다이렉션은 3xx 결과에 Location 헤더가 없으면, Location 위치로 자동이동 하는것을 뜻한다.  

- 영구 리다이렉션 - 특정 리소스의 URI가 영구적으로 이동
  - 예) /members -> /users
  - 예) /event -> /new-event
- 일시 리다이렉션 - 일시적인 변경
  - 주문 완료 후 주문 내역 화면으로 이동
  - PRG: Post/Redirect/Get
- 특수 리다이렉션 
  - 결과 대신 캐시를 사용


## 내용이 너무 딥한것같아서 실습후 이어하기