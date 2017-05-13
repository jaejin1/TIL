#### NPM( Node Package Manager )

#### NPM 독립적인 앱 설치

 ##### Ex) uglify-js 

* 설치   
	
	> npm install uglify-js -g
	
* 사용

	> uglifyjs pretty.js
		
	문맥상의 들여쓰기나 띄어쓰기등을 지워줌 
		
	> uglifyjs pretty.js -m 
		
	변수들 이름을 한글자로 줄여주는 옵션 
		
* 보통 많이 쓰는 방법은 

	> uglifyjs pretty.js -o pretty.min.js -m
		
	이렇게 많이 쓰임.
			
[uglify-js 문서](https://www.npmjs.com/package/uglify-js)
 
	
#### NPM으로 모듈설치

우리의 소프트웨어를 패키지로 지정하기위한 환경설정 

> npm init

package.json 이란 파일을 생성해주는 역할

npm의 패키지의 디렉토리로 설정한거임.

* 설치

	> npm install underscore
	
	다운을 받으면 node_modules폴더에 underscore란 폴더가 생성된다.
	
	> npm install underscore --save
	
	package.json 에 'dependencies' 가 추가 된다. 추가했으면 언제든지 포함시킬수잇다. 
	
	소스코드에 필요없는데 순간적으로만 사용할때는 --save를 빼고 반듯이 포함해야할때만 사용한다.
	
* 사용
	
	> require('underscore');
	
	underscore을 사용하기위한 객체를 반환한다.
	
	Ex)   
	
	~~~
	var _ = require('underscore');
	var arr = [3,6,9,1,12];
	console.log(arr[0]);

	console.log(_.first(arr));

	console.log(arr[arr.length-1]);

	console.log(_.last(arr));
	~~~
	
	반환값 = 3 3 12 12
	
[underscore 문서](http://underscorejs.org/#first)