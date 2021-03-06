---
layout: post
title: '웹 기본 지식'
date: 2020.07.11
author: IraJane
tags: WEB-HACK
---
<h5>uri 구성 요소</h5><br>
<br>
http://example.com:80/path?search=1#fragment<br>
scheme // host / path ? query # fragment <br>

<br>
<b>인코딩</b> :보안 등의 목적으로 다른 방식으로 처리하는 것 - 인코딩 한 것을 원래 형태로 변경하는 것은 디코딩이라고 함 <br>
<b>인크립션</b> :양방향 암호 알고리즘<br>
<br>

- uri encoding : 서버 내에서 데이터를 처리할 수 있게 해준다 <br>
- HTML entity Encoding : 문서 내에서 사용하는 문자들이 html에서 사용하는 테그로 인식되지 않게 <br>
<br>
<b>HTTP</b>와 <b>HTTPS</b>는 scheme(protocol)에 해당됨 <br>
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
http는 하나의 request와 response의 쌍이 독립적으로 구성되어 통신하는 connectionless, stateless 프로토콜로 이루어져있음  
<br>
connectionless : 한개의 요청 처리 후 연결 끝냄 <br>
-서버에서 다수의 클라이언트와 연결을 유지해야 한다면 많은 리스소가 발생하고 리소스를 줄이면 더 많은 연결을 할 수 있다 <br>
- 연결/해제에 대한 오버헤드(처리를 하기 위해 들어가는 간접적인 처리시간 혹은 메모리)가 발생할 수 있다 <br>
<br><br>

keepAlive : 지정된 시간동안 서버와 클라이언트 사이에  패킷 교환이 없는 경우 패킷을 주기적으로 보내는데 패킷에 반응이 없으면 접속을 끊음 <br>
       : 패킷이란 데이터 묶음 단위로 한번에 전송할 데이터의 크기를 나타냄 <br>
       제 3계층 이상에서는 데이터 묶음을 패킷이라고 부르고 제 2계층에서는 프레임이라고 부름 <br>
       패킷단위로 데이터를 나누어 보내야 하는 이유는 한번에 많은 데이터를 한곳에 보내다가 에러가 나면 다른 곳들은 대기를 해야 하고, 보내다가 오류가 나면 처음부터 다시 시작해야 하기 때문에 이때 발생하는 문제를 해결할 수 있게 해준다 <br>
메모리를 많이 사용한다 <br>
<br><br>

stateless : connectionless로 인해 서버가 클라이언트를 식별할 수 없는 상태<br>
<br><br>

상태를 기억하는 방법 

    1. 쿠키 : 클라이언트 측에서 관리되는 작은 기록 정보 파일을 의미함
             유효 시간 명시할 수 있으며 브라우저를 끄더라도 유효시간 안에는 인증이 유지됨 
             http헤더 set-cookie
             사용자 정보가 브라우저에 저장이 되기 때문에 보안에 취약
            
    2. 세션 : 서버단에 사용자 정보를 저장해서 쿠키보다 안전 
             동시 접속자 수가 많은 서비스의 경우 서버 과부화의 원인이 됨 
             로그인 처럼 보안상 중요한 작업을 수행할 때 사용함 
             
    3. 토큰 기반(OAuth, JWT) : 보호할 테이터를 토큰으로 치환하여 원본 데이터 대신 토큰을 사용
              보안성 높음 
              
              -- OAuth : 사용자 인증을 하기 위해 다른 어플리케이션의 사용자 인증방식을 사용하도록 인가함
                           => 사용자 인증 프로토콜이 아닌 인가 프로토콜
              
              --JWT(JSON Web Token): 토큰 자체가 의미를 갖는 권한기반 토근 
                    정보가 담긴 데이터를 암호화하여 http헤더에 추가시킴
                    보안에 완벽한 것은 아니기 때문에 유효시간을 짧게 설정해줘야 한다 
                    HMAC(Hash-based Message Authentication) 
                            =>토큰이 탈취당하더라도 위변조하기 힘들도록 무결성을 보장하는 방법 중 한개 
                            (해싱은 원문이 조금이라도 바뀌면 해싱의 결과가 달라지기 때문에 위조된 것을 알 수 있다 )
                    
                    
<br>
HTTP는 모든 데이터가 암호화없이 전송이 된다 <br>
HTTPS는 SSL을 사용하여 암호화를 한다.




<br>





<br>





<br>




<br>
[참고]<br>
https://dreamhack.io/<br>
https://victorydntmd.tistory.com/4<br>
https://victorydntmd.tistory.com/115<br>



<br>
