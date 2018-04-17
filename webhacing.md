# Basic
- 풀이

 Find the flag this page
 Flag Structure : flag is {real flag}
 ~~~html
<!--flag is {W3b_is_S1mp1e}-->
~~~
이 페이지의 소스코드를 살펴보면 맨 뒤부분에 위와 같은 코드가 있다.

이것을 보면 flag는 ' W3b_is_S1mp1e ' 인 것을 알 수 있다.
- 정답

  W3b_is_S1mp1e

# Connect
- 풀이

페이지에 처음 들어가면 

Referer : wantconnection

User-Agent : iwant!!!!

Go!

위와 같은 화면이 나타납니다.

먼저 Go!로 이동한다음에 

fiddler4를 켜서 Raw부분에서 referer과 user-agent부분을 

각각 wantconnection , iwant!!!!로 바꾼 뒤

replay를 하면 replay된 곳의 webveiw 부분에 다음과 같이 키값이 나와 있습니다. 

Key is Us3r_Ag3nt_@nd_R3f3r3r 

- 정답

   Us3r_Ag3nt_@nd_R3f3r3r

 # Find

 - 풀이

 페이지에 들어가면 prob링크가 있다. 이것을 클릭하면 게임판이 보인다. 

이 곳의 소스파일을 보면 다음과 같은 부분이 보인다.

~~~html
 <input type="hidden" name="HaHa" value="MA==">
 ~~~
이 소스에서 type을 submit으로 바꾼다. 
~~~html
<input type="submit" name="HaHa" value="MA==">
~~~

이렇게 하면 MA==라는 버튼이 생기는데 이것을 누르면 점수가 1점증가한다.
이 행위를 1000정도 반복하면 1000점을 채울 수 있다. 
 
# Web1_Project3
- 풀이

이 페이지에 들어가면 관리자 로그인하는 곳이 보인다. 아마도 로그인을 하면 해결되는 문제인 것 같다.

그리고 이 페이지의 소스코드를 보면 주석 부분에 다음과 같은 부분이 있다. 
~~~html
<!--
	Test Account : admin/admin123
	--> 
~~~
이것을 보고 로그인을 하면 키 값을 알 수 있다. 
- 정답

  Unc0mpleted_Devel0pment 
# Web2_Project3
- 풀이

이 페이지에 처음 들어가면 " Plz POST me T.T "라는 문자 외엔 아무것도 보이지 않는다. 소스코드도 깨끗했다.

이때 POST는 HTTP프로토콜을 이용하여 서버에 정보를 전달하는 방법이다. 이 방법에는 GET이라는 방법도 있다.

이것으로 보아 GET으로 되어있는 부분을 POST로 바꾸면 풀 수 있을 것 같다. 

그래서 fiddler4를 이용하여 풀기로 했다. 들어가서 Raw부분을 보면 GET이라고 써져있는 것이 보인다. 

이 GET부분을 POST로 바꾸고 replay를 해서 보면 다음과 같은 키값이 나온다. 

KEY is : p0s7_m3_1f_y0u_can 
- 정답

  p0s7_m3_1f_y0u_can 

# Web3_Project3

  - 풀이 
 
 페이지에 처음 들어가면 " 이 페이지에서 이미 키를 드렸습니다. "라는 메세지가 보인다. 

 그것을 확인하기 위해서 페이지 검사 →network에 들어가서 F5, indes.php를 보면 
 Key: thisisKey라는 부분이 있다. 
 
 이것을 보아 키값은 thisiskey라는 것을 알 수 있다.

 - 정답

   thisiskey

 # Web4_Project3

 - 풀이

처음에 들어가면 보이는 사이트의 url을 보면 다음과 같은데 

hxxp://wargame_sec.xxxxxx.xx.kr/web/web4_DJU/index.php

각각의 항목을 눌러보면 
\\\\  ?game=<   >  \\\\\ <>의  값이 각 항목에 맞춰져서 바뀌는 것이 보인다. 

그래서 <>에 flag을 입력했더니 다음과 같은 키값이 나온다. 

Key is : L0cal_F1l3_1nclus10n!!

- 정답

  L0cal_F1l3_1nclus10n!!

# Web5_Project3

  - 풀이 

LFI는 로컬의 파일을 포함시킨다는 뜻이다. 

LFI취약점이 있다면, 서버에서 제공하는 디렉토리 외 로컬 영역의 디렉토리와 폴더를 열람할 수 있다.

이 취약점을 이용하면 상위 디렉토리로 이동이 가능한데 이 문제를 풀 때 PHP Wrapper을 이용하면 된다. 

그중 php://filter를 사용하는 방법이다.

다음을 빈칸에 입력하면 base64로 인코딩된 php소스가 나온다.

php://filter/convert.base64-encode/resource=index.php

그 소스는 다음과 같다.

PD9waHAKCS8vIEtleSBpcyA6IExGSV9XSVRIX0JBU0U2NF9JU19WRVJZX0RBTkdFUk9VU18hCj8+CjxodG1sPgoJPGhlYWQ+CgkJPHRpdGxlPndlYjA1PC90aXRsZT4KCQk8c3R5bGU+CgkJCWh0bWwsIGJvZHl7CgkJCQl3aWR0aDogMTAwJTsKCQkJCW1hcmdpbjogMDsKCQkJCXBhZGRpbmc6IDA7CgkJCQl0ZXh0LWFsaWduOiBjZW50ZXI7CgkJCX0KCQkJYm9keXsKCQkJCW1hcmdpbi10b3A6IDQwcHg7CgkJCX0KCQkJLm91dHB1dHsKCQkJCXdpZHRoOiA4MDBweDsKCQkJCWhlaWdodDogMTIwcHggIWltcG9ydGFudDsKCQkJCWJvcmRlcjogMXB4IHNvbGlkICNhYWE7CgkJCQltYXJnaW46IDAgYXV0byAyMHB4IGF1dG87CgkJCQlvdmVyZmxvdy15OiBzY3JvbGw7CgkJCX0KCQkJLnNvdXJjZXsKCQkJCXdpZHRoOiA1MDRweDsKCQkJCW1hcmdpbjogMjBweCBhdXRvOwoJCQl9CgkJPC9zdHlsZT4KCTwvaGVhZD4KCTxib2R5PgoJCTxoMT5MRkkgKExvY2FsIEZpbGUgSW5jbHVzaW9uKTwvaDE+CgkJPGZvcm0gbWV0aG9kPSJnZXQiPgoJCTxpbnB1dCB0eXBlPSJ0ZXh0IiBuYW1lPSJ1cmwiLz4KCQk8aW5wdXQgdHlwZT0ic3VibWl0IiB2YWx1ZT0iVmlld0ZpbGUiPgoJCTwvZm9ybT4KCQk8ZGl2IGNsYXNzPSJvdXRwdXQiPgoJCQk8P3BocAoJCQkJaWYoaXNzZXQoJF9HRVRbInVybCJdKSAmJiAhZW1wdHkoJF9HRVRbInVybCJdKSl7CgkJCQkJJGVzY2FwZV9wYXR0ZXJuID0gYXJyYXkoImV0YyIsInBhc3N3ZCIsICJpbmkiLCAiJSIsICIvIik7CgkJCQkJaWYoaW5fYXJyYXkoJF9HRVRbInVybCJdLCAkZXNjYXBlX3BhdHRlcm4pKXsKCQkJCQkJZWNobyAiTm8gSGFja34hIjsKCQkJCQkJZXhpdDsKCQkJCQl9CgkJCQkJaWYoIWZpbGVfZXhpc3RzKCRfR0VUWyJ1cmwiXSkpewoJCQkJCQllY2hvICJObyBGaWxlIEV4aXN0cyFcbiI7CgkJCQkJfQoJCQkJCWluY2x1ZGUgJF9HRVRbInVybCJdOwoJCQkJfWVsc2UgaWYoaXNzZXQoJF9HRVRbInVybCJdKSAmJiBlbXB0eSgkX0dFVFsidXJsIl0pKXsKCQkJCQllY2hvICJFbXB0eSEiOwoJCQkJfQoJCQk/PgoJCTwvZGl2PgoJCTxocj4KCQk8ZGl2IGNsYXNzPSJzb3VyY2UiPgoJCQlpbmRleC5waHAgU09VUkNFPGJyIC8+CgkJCTw/cGhwCgkJCQlpbmNsdWRlICIuL3NvdXJjZS5odG1sIjsKCQkJPz4KCQk8L2Rpdj4KCTwvYm9keT4KPC9odG1sPgo=

이것을 디코딩하면 다음과 같은 소스파일이 나온다. 이 소스파일의 주석부분을 보면 키값을 알 수 있다. 

~~~html
<?php
	// Key is : LFI_WITH_BASE64_IS_VERY_DANGEROUS_!
?>
<html>
	<head>
		<title>web05</title>
		<style>
			html, body{
				width: 100%;
				margin: 0;
				padding: 0;
				text-align: center;
			}
			body{
				margin-top: 40px;
			}
			.output{
				width: 800px;
				height: 120px !important;
				border: 1px solid #aaa;
				margin: 0 auto 20px auto;
				overflow-y: scroll;
			}
			.source{
				width: 504px;
				margin: 20px auto;
			}
		</style>
	</head>
	<body>
		<h1>LFI (Local File Inclusion)</h1>
		<form method="get">
		<input type="text" name="url"/>
		<input type="submit" value="ViewFile">
		</form>
		<div class="output">
			<?php
				if(isset($_GET["url"]) && !empty($_GET["url"])){
					$escape_pattern = array("etc","passwd", "ini", "%", "/");
					if(in_array($_GET["url"], $escape_pattern)){
						echo "No Hack~!";
						exit;
					}
					if(!file_exists($_GET["url"])){
						echo "No File Exists!\n";
					}
					include $_GET["url"];
				}else if(isset($_GET["url"]) && empty($_GET["url"])){
					echo "Empty!";
				}
			?>
		</div>
		<hr>
		<div class="source">
			index.php SOURCE<br />
			<?php
				include "./source.html";
			?>
		</div>
	</body>
</html>
~~~

- 정답

  LFI_WITH_BASE64_IS_VERY_DANGEROUS_!



