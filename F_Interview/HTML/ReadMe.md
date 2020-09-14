# HTML 질문

- DOCTYPE은 무엇을 하나요?
- 여러 언어로 되어 있는 콘텐츠의 페이지를 어떻게 제공하나요?
- 다국어 사이트를 디자인하거나 개발할 때 주의해야할 사항은 무엇인가요?
- data-속성은 무엇에 좋은가요?
- HTML5를 개방형 웹 플랫폼으로 간주할 때, HTML5의 구성 요소는 무엇인가요?
- cookie, sessionStorage, localStorage 사이의 차이점을 설명하세요.
- \<script>, \<script async>, \<script defer> 사이의 차이점을 설명하세요.
-  왜 일반적으로 CSS \<link> 태그를 \<head>\</head> 태그 사이에 위치시키고, JS \<script> 태그를 \</body> 직전에 위치시키는 - 것이 좋은 방법인가요? 다른 예외적인 상황을 알고있나요?
- 프로그레시브 렌더링이 무엇인가요?
- 이미지 태그에 srcset 속성을 사용하는 이유는 무엇인가요? 이 속성의 컨텐츠를 실행할 때 브라우저의 프로세스를 설명하세요.
-다른 HTML 템플릿 언어를 사용해본 적이 있나요?

## 원본 글 출처
---
- 제가 중요하다고 생각하는 부분만 정리해 봤습니다.
https://velog.io/@chris/front-end-interview-handbook-html#doctype%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%84-%ED%95%98%EB%82%98%EC%9A%94


## DOCTYPE은 무엇을 하나요?
---
DOCTYPE은 document type의 약어입니다.
DOCTYPE은 항상 DTD(Document Type Definition)와 관련됩니다.
DTD는 특정 문서가 어떻게 구성되어야 하는지 정의합니다.

``<!DOCTYPE 'html'>``


## 여러 언어로 되어 있는 콘텐츠의 페이지를 어떻게 제공하나요?
---

 반환된 HTML 문서는 \<html lang="en">...\</html>과 같이 \<html> 태그에 lang 속성을 선언해야 합니다.

백엔드에서, HTML 마크업은 YML 또는 JSON 형식으로 저장된 특정 언어에 대한 i18n placeholder와 내용을 포함합니다. 그 다음 서버는 일반적으로 백엔드 프레임워크의 도움을 받아 특정 언어로 HTML 페이지를 동적 생성합니다.

## 다국어 사이트를 디자인하거나 개발할 때 주의해야할 사항은 무엇인가요?
---
<i>저는 이부분에 별로 큰 비중을 두진 않았습니다.</i>
- HTML에 lang 속성을 사용합니다


## data-속성은 무엇에 좋은가요
---
JavaScript 프레임워크가 인기있기 전에, 프론트엔드 개발자는 비표준 속성, DOM 추가 프로퍼티 등의 조작없이, DOM 자체에 추가적인 데이터를 저장하기 위해 data-속성을 사용했었습니다. 이는 적절한 속성이나 요소가 없는 페이지나 애플리케이션에 사용자정의 데이터를 비공개로 저장하기 위한 것입니다.
<br>
<br>
data태그에 관한 내용은 여기를 참고해 주세용
- https://developer.mozilla.org/ko/docs/Learn/HTML/Howto/%EB%8D%B0%EC%9D%B4%ED%84%B0_%EC%86%8D%EC%84%B1_%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0


## HTML5를 웹 개방형 플랫폼으로 간주할때 HTML에 구성요소는 무엇인가요?
<i>저는 이부분에 별로 큰 비중을 두진 않았습니다.</i>

- 연결 - 새롭고 혁신적인 방법으로 서버와 통신할 수 있도록 허용합니다.
- 성능과 통합 - 컴퓨터 하드웨어의 성능 최적화와 개선으로 더 나은 사용을 제공합니다.
- 장치 접근 - 다양한 입출력 장치의 사용을 허용합니다.

## <script>, <script async>, <script defer> 사이의 차이점을 설명하세요.
---
- \<script> - HTML 파싱이 중단되고, 스크립트를 즉시 가져오고 실행되며, 스크립트 실행 후 HTML 파싱이 다시 시작됩니다.
- \<script async> - 이 스크립트는 HTML 파싱과 병렬적으로 가져오며, 가능할 때 즉시 실행됩니다(아마 HTML 파싱이 끝나기 전).
- \<script defer> - 이 스크립트는 HTML 파싱과 병렬적으로 가져오지만, 페이지 파싱이 끝나면 실행됩니다.

## 왜 일반적으로 CSS <link> 태그를 <head></head> 태그 사이에 위치시키고, JS <script> 태그를 </body> 직전에 위치시키는 것이 좋은 방법인가요? 다른 예외적인 상황을 알고있나요?


- <link>를 <head> 안에 넣는 것은 최적화된 웹사이트를 구출할 때 적절한 명세의 일부입니다. 페이지가 처음로드되면 HTML과 CSS가 동시에 파싱됩니다.