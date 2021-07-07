# CNN



## 사각피질



![image-20210707131706229](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707131706229.png)

![image-20210707131743171](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707131743171.png)



## 합성곱층



### CNN 구조

![image-20210707131942879](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707131942879.png)



![image-20210707131959688](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707131959688.png)



### 합성곱연산

![image-20210707132050645](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707132050645.png)



![image-20210707132118673](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707132118673.png)

**커널을 n번 적용할 경우 Output의 크기**

​		 > 9 * 9 --> 5 * 5 --> 3 * 3 --> 1 * 1



​	![image-20210707132303999](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707132303999.png)



![image-20210707132345647](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707132345647.png)



![image-20210707132538655](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707132538655.png)



+ 고전적인 필터들은 사람들이 직접 고안해 내었다. 

  > ex) blur 처리를 하려면 gaussian filter를 연구, outline 필터를 만드려면 sober필터를 연구 등등

+ 최근에는 필터들을 학습시킴. (Automatically learned filter)





### 합성곱식

![image-20210707132626270](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707132626270.png)



+ 식을 보면 계속 공부했다 싶이 가중합과 편향을 더하는 꼴이란 것을 확인할 수 있음. 
+ l = 합성곱층, k = 특성 맵, i = 특성맵의 행, j = 특성맵의 열
+ 합성곱 층 l에 있는 k 특성 맵의 i행, j열에 위치한 뉴런은 이전 l-1 층에 있는 모든 특성 맵의 i * sh에서 j * sh + fh -1 까지의 행과 i * sw에서 j * sw + fw -1 까지의 열에 있는 뉴런의 출력에 연결된다. 
+ 다른 특성 맵이더라도 같은 i행과  j열에 있는 뉴런이라면 정확히 이전 층에 있는 동일한 뉴런들의 출력에 연결됨



**tesorflow keras - Conv2d**

`conv = keras.layers.Conv2D(filters =32, kernel_size = 3, strides = 1, padding = "same", activation = "relu")`

- 필터의 수, 커널의 크기, 스트라이드 값, 패딩 값, 활성화 함수 등등
- **이 convolution layer 파라미터의 수는?**



**Same vs Valid 패딩**

+ Same: 제로 패딩이라고 하며, (출력의 사이즈 = 입력의 사이즈)를 맞춰주기 위해서 자동적으로 0으로 패딩을 넣어줌

  > 간혹 stride 크기로 인해서 same패딩이라고 지정을 해주었지만 출력 사이즈와 입력 사이즈가 다를 수 있음

+ Valid: 패딩 없음

### 

## 풀링층



![image-20210707134522412](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707134522412.png)

+ 보통 cnn에서 이미지 특성 크기를 줄이는데 사용

  

![image-20210707134619671](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707134619671.png)





## CNN 기본 구조

![image-20210707134718918](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707134718918.png)

+ 기본 구조: 합성 곱층, 풀링층





![image-20210707134753990](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707134753990.png)

+ 합성곱층 + 풀링층 하나씩을 layer 하나라고 한다. 후에 fully connected (다층 퍼셉트론) 부분을 다른 한 layer로 본다. 

  > 합성곱층 + 풀링층!!! (한 세트)





![image-20210707134809995](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707134809995.png)

+ parameter 계산 방법... 





## 고급 CNN 

![image-20210707135155047](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135155047.png)



+ CNN구조에서는 ILSVRC ImageNet 대회 분류 작업 top-5에러율을 차지한 영향력 있는 "AlexNet, GoogleNet, ResNet을 위주로,,," + (cnn의 근본 LeNet-5) 도 같이 공부

+ 개인적으로 miniVGGNet도 혼자서 공부하는게 좋을 듯





### LeNet-5



![image-20210707135428159](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135428159.png)



### AlexNet

![image-20210707135447233](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135447233.png)



**AlexNet에서 주요하게 볼 것**



![image-20210707135519952](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135519952.png)



![image-20210707135632836](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135632836.png)





### GoogleLeNet

![image-20210707135704317](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135704317.png)



+ 인셉션 모듈의 큰 특징은 같은 크기, 사이즈의 출력들을 깊게 이어 붙힌다!

+ "SAME" 패딩으로 2번째 layer들의 필터 사이즈가 다 달라도 출력의 사이즈는 다 같으니 깊게 이어 붙힐 수 있음.

  

![image-20210707135722414](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135722414.png)

+ 1x1 커널을 왜 사용? 1x1커널을 생각해보면 한 픽셀씩 읽어들여서 무슨 특징을 잡을 수 있는지에 대한 궁금증,,,,,,,,



![image-20210707135745271](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135745271.png)



+ 위의 그림을 보면 왼쪽에 인셉션 모듈을 사용하지 않게 될때의 파라미터 개수는 (3x3x16) x 32 = 4608

+ 오른쪽의 파라미터 개수는 (1x1x16x5) + (3x3x5x32) = 1520

  **적은 파라미터의 개수로 더 강력한 패턴을 갖는 특성맵을 얻을 수 있음**

  

![image-20210707135803352](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135803352.png)



![image-20210707135816313](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135816313.png)





### ResNet

+ 레이어들을 깊게 만들고 싶다는 생각

![image-20210707135839741](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135839741.png)



![image-20210707135853792](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135853792.png)



![image-20210707135903646](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135903646.png)

+ 왼쪽의 그림은 output에 가까울 수록 gradient가 0의 값에 가깝게 변하게 됨 --> backpropagation을 진행할 수 없게된다. 
+ 깊은 레이어에서는 gradient 가 0이 되는 일이 잦음--> gradient 소실 문제
+ 즉 skip connection을 사용하여 gradient가 0과 가까우면 그 unit을 backpropagation에서 건너뜀



![image-20210707135913401](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135913401.png)



![image-20210707135928941](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135928941.png)





![image-20210707135938482](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20210707135938482.png)
