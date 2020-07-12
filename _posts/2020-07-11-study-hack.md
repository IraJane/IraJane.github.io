---
layout: post
title: '해킹 강의1'
date: 2020.07.11
author: IraJane
tags: WEB-HACK
---
<br>
https://dreamhack.io/<br>
<br>
<h5>uri 구성 요소</h5><br>
<br>
http://example.com:80/path?search=1#fragment<br>
scheme // host / path ? query # fragment <br>

<br>
<b>인코딩</b><br>
  :보안 등의 목적으로 다른 방식으로 처리하는 것 - 인코딩 한 것을 원래 형태로 변경하는 것은 디코딩이라고 함 <br>
<b>인크립션</b><br>
  :양방향 암호 알고리즘<br>
<br>
- uri encoding : 서버 내에서 데이터를 처리할 수 있게 해준다 <br>
- HTML entity Encoding : 문서 내에서 사용하는 문자들이 html에서 사용하는 테그로 인식되지 않게 <br>
<br>
HTTP와 HTTPS는 scheme(protocol)에 해당됨 <br>
데이터의 교환 방식을 결정하는 부분<br>
TCP(데이터를 주고받는 통신 규약) 또는 TLS(암호화 TCP)를 사용, 기본 포트는 80, 443 <br>
<br>
<b>Status code</b> : 사용자의 요청에 대한 서버의 처리 결과 <br>
200 - 요청에 대한 서버 처리 성공<br>
300 - 요청한 리소스가 다른 경로로 변경된 경우<br>
400 - 구조 또는 데이터가 잘못됨 <br>
500 - 서버의 에러<br>
<br><br>

<b>Header</b><br>
content-type : 서버의 응답 데이터를 웹 브라우저에서 처리할 방식과 형식을 나타냄<br>
content-length : 서버가 사용자에게 응답해주는 데이터 길이<br>
server : 서버가 사용하는 소프트웨어의 정보<br>
location : 300번 영역의 응답코드 사용시 웹 리소스의 주소를 나타냄<br>
set-cookie : 사용자에게 쿠키를 발급할 때 사용 <br>


<br>



<br>





<br>





<br>





<br>




<br>




<br>
