#### 동기와 비동기


바로 예시로 보자

~~~
var fs = require('fs');

// Sync
console.log(1);
var data = fs.readFileSync('data.txt', {encoding:'utf8'} );
console.log(data);


// Async
console.log(2);
fs.readFile('data.txt', {encoding:'utf8'}, function(err, data){
  console.log(3);
  console.log(data);

});
console.log(4);
~~~

이런 코드가 있을때 결과값은 

> 1  
	data.txt 내용  
	2  
	4  
	3  
	data.txt 내용

이렇게 출력이 된다.

왜냐하면 Sync(동기) 처리는 순서 대로 처리된다보고

Async(비동기)는 fs.readFile()의 작업이 Background에서 작업되고 마친 후에 결과가 출력이된다.


**이것이 중요한이유**는 WebApp에서 파일을 읽는 작업이 시간을 많이 잡아먹을때 동기식으로 처리하면 서버에서 파일을 읽을 시간동안 아무것도 하지 못하게 된다.

node.js은 거의다 비동기식으로 처리되기 때문에 장점이라고 볼수있다.