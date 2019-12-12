# 웹 크롤링 주제 : 항공권 가격변동 추적
##### 항공권은 한 달전에 사는것과 두 달전에 사는게 다른데 언제 최저가가 될까?
<center><img src = "/img/aurora.jpg"></center>

### 배경

- 데이터사이언스 과정이 끝나면 오로라를 보러 가볼까
- 출발일(예 2020년 2월 19일)이 같더라도 언제 예매하느냐에 따라 항공권 가격은 변함
- 예시
<center><img src = "/img/trend.png"></center>
출처 : https://brunch.co.kr/@handae/20

### 방법
- 하루 한 번 가격과 예매처 정보를 불러들여서 Database에 저장

### 필요한 데이터 
<center><img src = "/img/naverflight.png"></center>

- 가격
- 크롤링 시각
- 항공편, 출발지, 도착지, 출발시각, 도착시각, 비행시간, 경유회수

### 자료수집 구조
<center><img src = "/img/f.PNG"></center>

### 결과
<center><img src = "/img/robo3t.PNG"></center>

### 어려웠던 점
- BeautifulSoup의 css selector 및 scrapy의 xpath로 수집불가
  - selenium 사용
- kayak데이터 수집불가
  - url을 flight.naver.com으로 변경
<center><img src = "/img/kayak_error.PNG"></center>

- 불규칙한 에러 발생 (어떨때는 되고 어떨땐 또 안되고)
  - driver.get(url) 이후 time.sleep(10) 사용
- crontab 경로
  - run.sh 에 크롤링 폴더경로를 전부 써 줘야 함
<center><img src = "/img/runsh.jpg"></center>

### 더 해봐야 할 점
- pipeline에 구글스프레드시트 추가
- boto3로 서버 껐다 켰다하면서 데이터 
