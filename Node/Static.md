#### 정적파일을 서비스 하기 

--

코드 

> app.use(express.static('public'));

public 폴더생성하고 파일을 넣었을때 정적으로 불러올수있음 

ex)
 
~~~
app.get('/route', function(req,res){
	res.send('Hello Router, <img src="/aaa.gif">')
})
~~~

[문서참고](http://expressjs.com/ko/starter/static-files.html)