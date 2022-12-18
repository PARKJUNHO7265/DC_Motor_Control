<h3>주제</h3>
DC 모터 제어
<h3>내용</h3>
DC 모터를 simulink를 활용해 모델링하고 입력전압에 따른 회전수를 살펴보자.
<h3>DC 모터 equation</h3>

![image](https://user-images.githubusercontent.com/87568714/208296974-5a7811d3-b510-45c0-a306-ab4fd6a9ebf6.png)

위 그림은 간단하게 표현한 DC모터 회로도이다.</br>
여기서 Va는 입력전압, R은 저항, L은 인덕터, V_emf는 역기전력, K_f는 부하저항, w는 각속도, T는 모터의 토크,</br>
K_t는 자속밀도, K_emf는 모터의 역기전력 상수, B는 모터의 마찰계수, T_l은 부하의 토크이다.</br>

Va 전압이 걸리면 저항과 인덕터에 전류가 흐르고 DC모터가 회전하게되는데 이때 역기전력 Vemf가 생성된다.</br>
따라서 전기적인 부분의 방정식은 다음과 같이 표현할 수 있다.</br>
V_a = R * i + L * di/dt + V_emf ~~~~ di/dt = -R * i/L - K_emf * w/L + V_a/L</br>

다음은 물리적인 부분의 방정식에 대해 생각해보자. 뉴턴의 제 2 법칙에 의하면 토크는 inertia 와 각가속도의 곱으로 표현된다.</br>
이를 DC모터에 적용하면 J * dw/dt = T - K_f ~~~~ dw/dt = K_t * i/J - B * w/J - T_l/J이다.</br>

<h3>DC 모터 Modeling</h3>
위 두 방정식을 활용하여 아래와 같이 모델링하였다.

![image](https://user-images.githubusercontent.com/87568714/208296366-84622032-2b0e-45ee-a4ae-b2b8e3ba350d.png)

<h3>DC 모터 시뮬레이션</h3>
입력전압 Va를 초기값이 12V이고 5초 뒤 최종값이 24V인 Step Function으로 주고 10초간 시뮬레이션 하였다.</br>
아래 그래프는 시간에 따른 모터의 RPM 그래프이다.

![image](https://user-images.githubusercontent.com/87568714/208296411-4c2b260b-b7f9-4d80-a88a-f26be5485713.png)

1에서 5초 동안 약 27RPM, 이후 전압이 증가하여 마찬가지로 RPM도 증가하다가 6초부터 54RPM인 것을 확인할 수 있다.</br>
따라서, 입력전압과 모터의 회전속도는 비례한다는 DC 모터의 특성을 잘 나타내고 있다. 
