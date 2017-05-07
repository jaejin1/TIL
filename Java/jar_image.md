### jar파일에 안올라가는 파일 경로추가하기

---


1. Properties -> Source -> Add Folder 에 폴더 추가하기

2. 코드수정 
	* 원래 코드가 **"test.png"** 였으면
	* **URL 변수 = class명.class.getClassLoader().getResource("test.png");**
	* "test.png"의 자리에 **URL 변수**로 바꾸기

그럼 잘된댱 헿
