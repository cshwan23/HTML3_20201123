# HTML3_20201123
HTML문법3_코딩

1. HTML_06_01 부터 코딩 다시 쳐보기


Chap. 6 

입력 양식 관련 태그

> 클라이언트한테 입력 받는 데이터
> 서버 간의 통신하는 역할을 하는 태그
> DB연동과 관련이 깊다.
> 프로젝트 설계 화면에서 DB설계와 더불어 제일 중요하다.
> 데이터베이스의 칼럼명과도 일치하고 관련성이 있다

1. 입력 양식 관련 태그

> 데이터를 입력 또는 선택할 수 있는 태그를 말한다.
> 입력, 선택한 데이터는 서버의 웹프로그래밍 언어로 전달되고 최종 DB에 저장된다.

2. 입력 양식 관련 태그 종류

> form
     > 여러 [입력 양식]을 1개의 그룹으로 묶는 태그이다.

> input
     > 데이터를 입력 또는 선택할 수 있는 [입력 양식]을 출력하는 태그다.

> select
     > 1개 이상의 목록 중 하나를 선택하는 [목록 상자]를 출력하는 태그다.

> option
     > select 태그 내부에서 사용되어 [목록 상자] 내부의 목록을 출력하는 태그다.

> textarea

ㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡㅡ

입력양식의 가장 중요한 것은 name 값과 value 값이다
최종 value 값은 내가 키보드에서 수정한 값이다.
틀리게 적으면 안된다 데이터베이스와 연관성이 있기 때문에

<form태그의 속성>

     <form name="memRegForm"
                action="http://www.naver.com"
                method="post"
                enctype="multipart/form-data"
     >

택배 보낼 물건을 택배상자에 넣듯 만들게 될 입력 양식 태그도 form 태그 내부에 삽입된다(form = 택배상자)

name : form 태그의 이름을 memRemForm으로 설정
action : form 태그 안의 입력양식에 입력(선택)된 데이터를 보낼 서버 쪽 url 주소를 설정
method : 입력(선택) 데이터를 서버로 보내는 방법을 설정
          > method="get"  : 입력(선택)된 데이터가 URL 뒤에 붙어 전송.
          > method="post" :  입력(선택)된 데이터가 안보이게 전송(보안성)
enctype : 전송될 데이터의 형식을 설정
          > enctype="multipart/form-data" : form 태그 내부에 <input type="file">태그가 있을 경우 파일도 전송가능

<해당 열의 text 타입 입력양식 >

     <td>
     <input type="text" name="userId" size="20" maxlength="10">
     </td>

한 줄의 [문자열]을 입력받는 양식 설정

<암호 입력양식>

     <input type="password" name="pwd" value="" size="20" maxlength="12">

> type 을 password 로 하면 바둑알이 들어간다
> size 는 가로로 크기를 설정하고
> maxlength는 최대 문자 개수를 설정한다 (지정하지않으면 무한대)

<전화번호 입력양식>

     <input type="text" name="phone" size="20" maxlength="15">

<체크박스 입력양식>

     <input type="checkbox" name="skill" value="JSP" checked>JSP
     <input type="checkbox" name="skill" value="ASP">ASP
     <input type="checkbox" name="skill" value="PHP">PHP

> value는 화면에 보이는 값이 아니다. 화면에 보이려면 >태그 밖에 써줘야 한다.
> checkbox 는 다중 선택이 가능하다. [다중체크입력방식]
> 체크박스로 받는 value 값은 배열로 받게 되어있다.
> [다중체크입력양식]은 이름이 2개 이상 동일해도 된다.
> name="" 값은 같아도 되지만 value 값은 달라야 한다.
> 이름이 같아도 다 전송되는 경우는 체크박스/라디오박스 두가지 뿐이다.
> default값으로 하나를 선택해서 보여주고싶을 때 <input checked>

<라디오 입력방식>

     <input type="radio" name="school" value="중졸">중졸
     <input type="radio" name="school" value="고졸" checked>고졸
     <input type="radio" name="school" value="대졸">대졸

> radio는 하나만 선택이 가능하다.[단일체크입력방식]
> 이것 또한 이름은 2개이상 동일해도 된다. 체크한 놈의 value 값만 다르면 
그 value 값만 서버로 전송된다. 
> radio 버튼은 여러개중 하나는 꼭 데이터로 보내야 될 때 사용.
> default값으로 하나를 선택해서 보여주고싶을 때 <input checked>

<목록상자 입력방식>

     <td>
     <select name="religion" size="5" multipled>
          <option value="" selected >선택요망</option>
          <option value="불교">불교</option>
          <option value="기독교">기독교</option>
          <option value="천주교">천주교</option>
          <option value="무교">무교</option>
     </select>
     </td>

> 입력 양식의 이름을 지정하고 주로 오라클 칼럼명과 일치한다.
> 라디오버튼 입력방식과 비슷하다.
> 라디오 상자는 무조건 1개만 선택해야하지만(단일선택)
> 목록상자는 비어있는 경우가 있다.(선택안해도된다)
> 목록의 수가 많다면 라디오보단 목록상자가 유리하다.
> 목록상자를 펼쳐보이게 하는방법 <select size="목록개수">
> 목록상자는 단일 선택이지만 다중선택도 가능하게 할 수 있다 <select multipled>
> 라디오상자/체크박스 두기능(이중성)
> 목록상자에서 디폴트값으로 하나를 선택해서 보여주고싶을 때(selected)
> option은 목록인데 옵션태그 안 value 값이 실제 db에 저장될 값이다.  


<파일(사진) 입력 양식 >

     <form enctype="multipart/form-data">
     <td>
          <input type="file" name="pic">
     </td>

> [파일입력상자] 는 절대로 키보드로 칠 수 없고 [찾아보기]를 클릭해야한다.
> <input type="file" name=""> 만 코딩하게되면 파일이 가는 것이 아니라
   파일 이름만 가게 된다. (파일업로드를 해야한다)
> 파일업로드를 하기위해선 택배상자에 취급주의 스티커가 붙듯 뭐가들어있는지 알수있듯이
  <form> 상자 안에 enctype="multipart/form-data"를 붙여야 진짜 파일이 간다.
     
<많은 문자열(메모장) 입력양식>

     <td>
          <textarea name="introduce" cols="20" rows="10">
          </textarea>
     </td>

> 다중문자열입력양식은 <textarea> 다.
> 좌우 크기를 길이를 줄일때는 size=""가 아니라 cols=""이다.
   (cols 는 한줄에 들어가는 글자 개수)
> 줄수를 조절할 때는 rows="" 이다.


<저장 버튼과 테이블 간의 간격을 세밀하게 조절하고 싶을때>
 

1. 빈 table을 만들어 높이를 준다

          <table><tr><td height="10"></td></tr></table>

테이블 태그도 독고다이 태그, 한행을 독차지하므로 자동으로 줄바꿈이 된다.

2. div 을 사용한다

          <div style="height:10pt;"></div>


<버튼 클릭시 이벤트실행 입력양식>

     <script>
          function checkMemForm(){
               var userId = document.regMemForm.userId.value;
               var regExp = new RegExp ( /^ [a-z][a-z0-9_]{4,9} $/ ) ;
               if(regExp.test(userId)==false){
                    alert("올바른 아이디가 아닙니다")
               }               
          }
     </script>
     <input type="button" value="저장" onclick="checkMemForm();">



[초기화 버튼 이벤트 입력양식]

     <input type="reset" value="초기화">

[서버로 보낼 주소를 설정하고 보내는 버튼 이벤트 입력 양식]

     <form action="http://www.naver.com">
     <input type="submit" value="저장">

[숨겨진 문자열 입력 양식]

     <input type="hidden" name="mem_no" value="11">

> 숨겨진 문자열 입력양식은 코딩을 해도 화면에 보이지 않는다
> 화면에 보일 필요는 없지만 꼭 서버로 보내고 싶은 데이터가 있을 경우
   hidden 안에 담으면 된다
> 보이지 않기 때문에 개발할 때 조심해야하는데 
   hidden 태그를 text 태그로 바꾼후 value 값을 눈으로 확인 후 
   다시 text태그를 hidden으로 바꾼다.
