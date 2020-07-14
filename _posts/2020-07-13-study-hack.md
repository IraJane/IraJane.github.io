---
layout: post
title: '웹해킹 기본'
date: 2020.07.13 
author: IraJane
tags: WEB-HACK
---
공부 일자 : 07.13 ~
<br><br>
<b>Same Origin Policy(SOP)</b><br>
-자바스크립트 또는 HTML 태그들을 이용해 나의 계정의 내용을 볼 수 있는 권한을 사용할 수 있게 되는데 그런 공격으로 부터 사용자를 보호하기 위해 만들어졌다.<br>
- 서로 다른 오리진(프로토콜, 포트, 호스트)의 문서 또는 스크립트 들의 상호 작용을 제한하기 위함이다 <br>
- 동일한 오리진이 아닌 다른 오리진(cross origin)이면 내용을 읽지 못하게 한다<br>
- 스크립트를 이용해 같은 오리진일 경우와 다른 오리진일 경우 다른 값을 출력한다 <br>
<br><br>
<b>Cross Origin Resource Sharing (CORS)</b><br>
- 일반적으로 SOP영향으로 서로 다른 오리진들과 리소스를 공유하지 못함<br>
- 하지만 공유를 해야 하는 상황이 발생한다 <br>
<br><br>
<b>postMessage</b> : 메세지를 주고 받기 위한 이벤트 핸들러를 이용해 리소스 공유<br>
<b>JSONP</b> : 스크립트 태그를 통해 다른 오리진 리소스를 요청 후 응답 데이터를 현재 오리진의 Callback 함수에서 다루는 방식을 통해 리소스 공유<br>
<b>CORS</b> 헤더 사용 : 다른 오리진이 허용하는 설정 등을 HTTP헤더를 통해 확인한 후 허용하는 요청을 보내 리소스 공유 <br>
          -서로 다른 스킴을 사용하면 웹 브라우저에서 허용하지 않을 수 있음 <br>


<br><br><br>
<h3>Cross Site Scripting(XSS)</h3><br>
임의의 악성 스크립트를 실행할 수 있음 - 이를 통해 쿠키나 세션을 탈취할 수 있음<br>
성공적으로 수행하기 위해서는 데이터를 주고 받을 때 충분한 검증과정이 없으면 된다<br>
- javascript 로 쿠키정보를 가지고 와서 해킹할 수 있음<br>
- Stored xss : 해커가 남긴 글을 읽으면 악성 스크립트가 실행되게 함<br>
- Reflected xss : 요청 데이터가 서버의 응답에 포함되는 과정에 악성 스크립트가 그대로 출력됨 <br>
<br><br>

해킹을 방지하기 위해 생겨난 방안들<br>
<b>1. Server-side Mitigations</b><br>
          태그 삽입을 방지하기 위해 서버 단에서 검증하는 방법<br>
          HTML Entity Encoding을 이요해 <>",'와 같은 특수문자를 태그로 인식이 안되게 설정 가능 <br>
          사용자 input에 HTML형태를 지원해야 한다면 화이트리스트 필터링을 해야한다<br>
                    =>주의할 점은 User-Agent나 Referer와 같은 헤더도 같이 필터링해줘야 한다 <br>
          
<b>2. HTTPOnly 플래그 사용</b><br>
<b>3. Content Security Policy 사용</b><br>
<b>4. X-XSS-Protection</b><br>




<br><br><br>


