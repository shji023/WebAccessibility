## 접근성의 개선이 필요하다고 생각하는 데이터테이블을 가진 웹페이지 선정
[[TOEIC 공식 사이트] 수험자가이드](https://exam.toeic.co.kr/common/template/viewContents.php?contentsCode=36)

## 웹 표준 준수 및 웹 접근성 관점에서 기존 서비스의 문제점 분석
데이터 테이블이 무엇이 관한 내용인지 이해할 수 있도록 <b>제목</b>을 제공해야한다.
  - summary 속성 
  - \<caption>
```
=> summary와 caption 태그가 존재하지 않는 문제
```  

데이터 테이블은 표의 네비게이션을 위하여 제목 셀과 내용셀을 구분할 수 있는 태그를 제공해야한다.
  - \<th>
  - \<td>
```
=> 가장 상단에 있는 제목 셀 (구분, 규정신분증, 대체 가능한 증명서) 은 th태그로 표현되었지만, 
왼쪽의 '구분'열에 있는 항목(대학생/일반인,초등학생,중학생/고등학생,군인,외국인.재외국민)들은 
규정 신분증,대체 가능 신분증을 기준으로 구분됨에도 불구하고 내용셀과 같이 td로 표현된 문제. 

=>'구분'열에 있는 항목들을 제목 태그로 표시 한 뒤 어느 부분의 제목인지 scope 태그로 지정 필요

=> 내용 셀을 표현하기 위해 tbody태그를 사용하였지만 
이에 상응하는 thead태그를 작성하지 않고 모든 표의 내용을 tbody태그에 넣은 문제. 

=> 표의 내용이 복잡하지 않아 id, headers속성을 사용하지 않았지만 
제목과 해당 내용 구분을 위해 사용하는 것도 좋을것이라 생각
```

링크 텍스트는 용도나 목적을 이해할 수 있도록 제공해야 한다.
```
테이블 안에 있는 링크의 역할(다운로드)이 명시되어있지 않는 문제
```

## WCAG에 맞춰 수정 계획 선정
### WCAG 분류
- 인식의 용이성(Perceivable): 정보와 사용자 인터페이스 요소는 사용자가 인식할 수 있는 방법으로 제시되어야 한다.
- 운용의 용이성(Operable): 사용자 인터페이스 구성요소 및 네비게이션은 운용 가능해야 한다.
- 이해의 용이성(Understandable): 사용자 인터페이스의 정보와 운용은 이해 가능해야 한다.
- 견고성(Robust): 콘텐츠는 보조공학을 포함한 다양한 사용자 에이전트가 해석할 수 있을 정도로 견고해야 한다.

```
한국형 웹 콘텐츠 접근성 지침에는 데이터테이블과 관련하여 
'(표의 구성) 표는 이해하기 쉽게 구성해야 한다'고 기재되어있다. 
이는 WCAG의 '이해의 용이성(Perceivable)'에 기반 한다. 
따라서 수정하고자 하는 페이지의 표는 이해하기 쉽도록 구성하며 관련한 충분한 정보를 제공할 계획이다.
```

## 웹접근성 관련 체크리스트 작성
- [x] summary 혹은 caption 태그 작성
- [x] th 와 td 태그 구분
- [x] tbody를 tbody와 thead로 분리
- [x] 적절한 scope사용
- [x] id, headers 속성 사용
- [x] a태그 download속성 추가

## 문법 검사 결과
- HTML
![html](https://user-images.githubusercontent.com/60960130/135885955-20605089-5fe5-4962-a38e-feb0cfb10749.PNG)

- CSS
![css](https://user-images.githubusercontent.com/60960130/135886035-647f9a3b-24d3-4c06-a578-624ddb5a35d2.PNG)

## 접근성 및 SEO 관련 분석 리포트 제출
- Lighthouse
  ![lighthouse](https://user-images.githubusercontent.com/60960130/135890578-6f5c1f9c-35ea-4fb2-a900-d313c2dbb274.PNG)

## 프로젝트 후기

위 프로젝트를 계기로 처음으로 웹접근성을 고려하며 웹페이지를 만들어보았다. 오직 테이블만 구성함에도 불구하고 생각해야할 요소가 많았다. <br />
그동안 div를 남발하며 의미없는 코드를 작성했던 습관을 고쳐야겠다고 느꼈다.  <br />
이미 많은 웹 사이트들의 코드가 웹접근성을 고려하여 작성되어있는 것을 보고 앞으로 HTML작업을 할때 필수적으로 웹접근성 고려해야겠다고 생각했다.

[참고 출처]
- https://www.w3.org/TR/WCAG21/#cc5
- [한국형 웹 콘텐츠 접근성 지침 2.1](http://www.kwacc.or.kr/Board/DataFile/669/Detail?page=1)
- https://exam.toeic.co.kr/common/template/viewContents.php?contentsCode=36