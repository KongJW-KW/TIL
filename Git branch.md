# 브랜치란?
Software개발시 개발자들은 동일한 소스코드 위에서 신규 개발, 버그 수정 등의 업무를 협업하곤 한다. 이럴 때, 여러 개발자들이 동시에 다양한 작업을 할 수 있게 만들어 주는 기능이 "Branch" 이다.

# 브랜치 확인하기
1) 현재 내가 위치한 Branch 확인 - $git branch</br>
![캡처](https://user-images.githubusercontent.com/80589627/125953998-cde9ba08-c623-4689-871c-0ad0f104db28.PNG)

2) 브랜치의 마지막 커밋 메시지 확인 - $git branch -v</br>
![캡처](https://user-images.githubusercontent.com/80589627/125954195-6ead4b1d-3d43-4d48-9f67-99866595d93c.PNG)

# 브랜치 삭제
git branch -d 브랜치명</br>
![캡처](https://user-images.githubusercontent.com/80589627/125954820-50681e17-abd3-4a29-b004-0774ceba6584.PNG)

# 브랜치 이동
git checkout 브랜치명</br>
![캡처](https://user-images.githubusercontent.com/80589627/125956557-a2447d11-2c4c-4b57-9f08-c3f765222f40.PNG)

# 브랜치 병합(merge)
1) 브랜치를 새로 생성한 다음 그 브랜치로 이동한다.</br>
![캡처](https://user-images.githubusercontent.com/80589627/125956774-72256408-c8a3-4da9-b9d7-9c121366ebba.PNG)

2) test브랜치에서 다음과 같은 함수를 작성하여본다. *파일명 test.js</br>
<pre>
function add (x, y){ 
  console.log(x); 
  console.log(y); 
  console.log(x + y);
  return x + y; 
}
</pre>

3) master branch로 이동</br>
![캡처](https://user-images.githubusercontent.com/80589627/125957401-e50db542-578e-4908-af79-eb7d6ad15787.PNG)

4) test브랜치에서 작업한 파일을 master브랜치로 병합</br>
![캡처](https://user-images.githubusercontent.com/80589627/125957660-c9db27fa-5ba0-452e-82ed-dde88f6ce473.PNG)</br>
**master브랜치에 test.js파일이 생성된 것을 확인 할 수 있다.**


