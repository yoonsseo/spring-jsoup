# spring-jsoup


## 크롤링(Crawling)과 스크래핑(Scraping)
#### 크롤링(Crawling)
* **URL을 탐색해 반복적으로 링크를 찾고 가져오는 과정**
* 링크를 타고 넘어가 반복적인 탐색 과정을 거치고, 한 번 거친 링크에는 색인(index)을 남김다 
* 일반적으로 검색 엔진 또는 봇(bot)이 웹에서 웹 페이지를 인덱싱하거나, 웹 사이트의 내용을 업데이트하고 주기적으로 새로운 콘텐츠를 찾는 데 사용된다
#### 스크래핑(Scraping)
* **특정 웹 페이지에서 데이터를 추출하는 것**
* ex. 특정 주제의 뉴스만 가져오기, 인기 검색어 정보 가져오기, 어떤 상품의 가격 모니터링


## Jsoup 라이브러리
**HTML을 파싱해주는 Java 오픈소스 라이브러리**  

**정적인 웹 페이지** 스크래핑에 사용되며, 웹 브라우저를 사용하지 않고도 HTML 문서를 파싱할 수 있다

* 동적인 웹 페이지는? → `Selenium` 라이브러리 이용
#### Jsoup 주요 객체/메소드
1. `Connection` : 연결을 하기 위한 정보(ex. URL)를 담고, 웹에서 content를 가져와 document로 파싱한다 
2. `Document` : Jsoup을 이용해 얻어온 결과로, URL과 연결해서 얻어온 HTML 전체 문서
3. `Elements` : Element가 모인 자료형으로, 반복문 사용이 가능하다
4. `Element` : Document의 HTML 요소
5. `Response` : Jsoup이 URL에 접속해 얻어온 결과로, Document와 다르게 status 코드, status 메시지나 charset같은 헤더 메시지와 쿠키 등을 가지고 있다
6. `select` 메소드 : HTML 문서 내에서 원하는 요소를 선택하기 위한 강력한 도구로, CSS 선택자를 사용해 요소를 찾을 수 있다
   ```Java
   Elements title = doc.select(".view_tit.no-margin-top.title_font_style");
   ```
   * dot(.)을 이용해 class 이름이 `view_tit.no-margin-top.title_font_style` 인 항목 가져오기
   * 샵(#)을 사용해 id 이름을 지정할 수 있고, 공백을 이용해 자식 요소를 선택할 수 있다
   * 이외에도 특정 태그나 속성만 선택하거나 복수의 요소를 지정할 수도 있고 다양한 문법을 제공한다
7. `getElementsByClass` 메소드 : HTML 요소의 클래스 이름을 기반으로 요소를 선택하는 메소드 

## Jsoup 사용법
#### 1. 의존성 추가 - gradle
```Java
implementation group: 'org.jsoup', name: 'jsoup', version: '1.15.3'
```
#### 2. URL 연결
```Java
String URL = "https://www.megabox.co.kr/theater/time?brchNo=1371";
Connection conn = Jsoup.connect(URL);
Document doc = conn.get();
```
  * URL 주소의 HTML 전체 내용이 document에 저장된다
  * 체인 형식으로 이으면 깔끔하다
#### 3. 타겟 element 파싱
```Java

```


## robots.txt
