## Machine Learning 개념

* Supervised learning

	하나의 정해져있는 데이터 (training set) 가지고 학습
	
* Unsupervised learning

	un-labeled data 데이터가지고 스스로 학습.
	

### Supervised Learning

* Traning data set
	
	 학습시키기 위한 데이터 셋
	 
* Types of supervised learning

	* 점수 같이 범위 나누는것 ( 0점 ~ 100점 )
	
		**Regression**
		
	*  Pass/non-pass 

		**binary classification**
		
	* Letter grade (A, B, C, E and F)

		**multi-label classification**

--- 

## TensorFlow

* Rank
	
| Rank  | Math entity  | Python example |
|:------------- |:---------------:| :-------------:|
| 0 | Scalar(magnitude only) |  s = 483 |
| 1 | Vector(magnitude and direction | v = [1.1, 2.2, 3.3] |
| 2 | Matrix(table of numbers)   | m=[[1,2,3],[4,5,6],[7,8,9]] |
| 3 | 3-Tensor(cube of numbers)  | t = [[[2],[4],[6]],[8],[10],[12]],[[14],[16],[18]]] |
| n | n-Tensor(you get the idea)   |  .... |

* Shapes
	
| Rank  | Shape  | Dimension number | Example |
|:------------- |:---------------:| :-------------:| :-----------: |
| 0 | [] |  0-D |  A 0-D tensor. A scalar |
| 1 | [D0] | 1-D | A 1-D tensor with shape [5] |
| 2 | [D0,D1] | 2-D | A 2-D tensor with shape [3,4] |
| 3 | [D0,D1,D2] | 3-D | A 3-D tensor with shape [1,4,3] |
| n | [D0,D1,...,Dn-1] |  n-D | A tensor with shape [D0,D1,...,Dn-1] |


1. 그래프 Build (placeholder 라는 노드를 만들수 있음)
2. Session을 만들고 run
3. update or return 된당.

~~~
node1 = tf.constant(3.0, tf.float32)
node2 = tf.constant(4.0)
node3 = tf.add(node1,node2)

print("node1: ", node1, "node2: ",node2)
print("node3 ", node3)

sess = tf.Session()
print("sess.run(node1,node2): ", sess.run([node1, node2]))
print("sess.run(node3): ", sess.run(node3))
~~~

* Placeholder

	먼저 노드 생성후 값을 넘겨줌 feed_dict로 인해
	
~~~
a = tf.placeholder(tf.float32)
b = tf.placeholder(tf.float32)

adder_node = a+b
sess = tf.Session()

print(sess.run(adder_node, feed_dict={a: 3, b: 4.5}))
print(sess.run(adder_node, feed_dict={a:[1,3], b: [2, 4]}))
~~~