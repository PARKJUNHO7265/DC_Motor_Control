<h3>주제</h3>
DC 모터 제어
<h3>내용</h3>
DC 모터의 회전수를 제어하는 모델을 설계하고 이를 이용하여 앞서 S_Hero에서 진행했던 프로젝트를 응용해보자.
<h3>DC 모터 equation</h3>

![image](https://user-images.githubusercontent.com/87568714/208278298-65eb905a-53f6-47df-b65e-2708a4fe6f0d.png)

위 그림은 간단하게 표현한 DC모터 회로도이다.</br>
여기서 Va는 입력전압, R은 저항, L은 인덕터, V_emf는 역기전력, K_f는 부하저항, w는 각속도, T는 모터의 토크,</br>
K_t는 자속밀도, K_emf는 모터의 역기전력 상수, B는 모터의 마찰계수, T_l은 부하의 토크이다.</br>
Va 전압이 걸리면 저항과 인덕터에 전류가 흐르고 DC모터가 회전하게되는데 이때 역기전력 Vemf가 생성된다.</br>
따라서 전기적인 부분의 방정식은 다음과 같이 표현할 수 있다.</br>
V_a = R * i + L * di/dt + V_emf ~~~~ di/dt = -R*i/L - K_emf*w/L + V_a/L</br>
다음은 물리적인 부분의 방정식에 대해 생각해보자. 뉴턴의 제 2 법칙에 의하면 토크는 inertia 와 각가속도의 곱으로 표현된다.</br>
이를 DC모터에 적용하면 J*dw/dt = T - K_f ~~~~ dw/dt = K_t*i/J - B*w/J - T_l/J이다.</br>
