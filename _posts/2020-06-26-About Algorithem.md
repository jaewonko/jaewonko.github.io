---
layout: single

title: "Readme"

categories : Algorithem

tags : Java

date : "2020-06-26"
---



반도체 집적회로의 성능이 24개월마다 2배로 증가하는 법칙

대략 y=2x의 꼴로 증가한다고 가정후
초기성능을 입력한다


 즉 어떤 랜덤한 인자값을 선택연산,교차연산,돌연변이후 본래 성능에 2배에 가까운 값을 찾은후

두번째 사이클에서 찾은값을 0번째배열에 집어넣어

또 다시 초기성능을 지정후에 반복한다 .  사이클이 돌떄마다의 초기성능을

저장해서 성능을 볼수있는 배열 하나를 또 선언한다

arr[8]생성

Arr 배열에 랜덤으로 인자값 (8비트내의수)를 집어넣고

첫번째 배열에 초기 성능을 입력한다

그후 선택연산의 과정에서 초기성능대비 2배의 가까운 값을 찾아내야하므로

arr[1]-arr[0] , arr[2]-arr[0] ~~~....arr[8]-arr[0] 값에다 나누기 arr[0]값을 했을때 

1근처의값을 찾아야한다 원래는  범위를 0.9~1.5 정도로 두고 혹시나 모든값이 범위에 해당하지않을경우

교차연산에서

더좋은 후보해를 찾기위해 진행하는 연산이 있다.

또 성능이 뒤떨어지는값이 나온경우 연산에서 제외한다


여기서 후보값을 찾고 더욱 좋은값을 찾기위해 교차연산을 진행한다

교차연산에서

최대한 2배의가까운 값을 찾아내기 위함이므로

나온 후보해들 중에 비트를 <<쉬프트시켜서 2배씩 증가시켜본다

예를들어 처음성능을 2로 가정

랜덤변수가 3 , 9 , 17, 20, 50 , 80 , 200 , 241 나왔다고 가정할경우

3-2 = 1       1/2 = 0.5
9-2 = 7      7/2 = 3.5
17-2 = 15    15/2 = 7.5
20-2 = 18    18/2 = 9
50-2 = 48    48/2 = 24
80-2 = 78     78/2 = 39
200 -2 = 198   198/2=99
241 - 2 = 239   239/2=119.5

교차연산을 진행하면

3이 후보해가 나오게되고 성능은 3으로 바뀌게된다 

또 랜덤변수가 1,5,6,16,20,50,70,147이 나온경우

1-3=-2 (x)
5-3= 2            2/3 = 0.66666
6-3 = 3       3/3 =1
16-3 = 13   13/3=4.33333
20-3 = 17   17/3=5.66666
50-3 = 47   47/3=15.6666
70-3 = 67   67/3=22.3333           101110 = 30
147-3 = 144   48          101011 = 27

후보해는 6이된다

여기서 돌연변이의 발생이 나타나는데 돌연변이의 경우 극단적인 성능저하를 막기위해

초기 사이클이 4번 돈후에 1/32의 확률로 발생한다고 가정하고

8자리비트중 뒤에 3비트 내에 0이 1로 1이 0로 성능이 올라갈수도 떨어질수도 있다.

만약 5번째 사이클에서  30의 성능을가진 반도체가 돌연변이가 발생하여 27이될수도있다.



 

   