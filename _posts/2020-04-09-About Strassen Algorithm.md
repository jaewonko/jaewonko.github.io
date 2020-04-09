---
layout : single

title : "About Strassen Algorithm"

categories : Algorithm

tags : Big O Algorithm

date : "2020-04-09"

---

###  Strassen Algorithm



***

원래 행렬의 곱셈은 

크기가 n x n인 두 행렬 A와B의 곱을 C로 나타내고자 한다.

![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkah4w8sovix.jpg%22&type=w2)의 원소를 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgk9ri3338ptm.jpg%22&type=w2)라 하고, ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkavqe24i89q.jpg%22&type=w2)는 가로 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkb607pg9oe3.jpg%22&type=w2)는 세로를 나타낸다.

B와 C도 동일하게 표시한다

.![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkdfr2qjsuqs.jpg%22&type=w2)

**** (이런식으로 표현되는데 사실무슨말인지 모르겠음 ㅠ)****

C하나의 원소를 구하는데 드는 비용은,

곱셈 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkijnwzd38sc.jpg%22&type=w2)번과 덧셈 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkiqe6ukvw79.jpg%22&type=w2)번이다.

따라서, C 전체를 구할 경우 C의 크기는 n x n 이므로

곱셈을 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkifggg728op.jpg%22&type=w2)번 그리고 덧셈을 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkizvgb1657n.jpg%22&type=w2)번하게 된다.

따라서, 두행렬을 구하는 복잡도는 ![img](https://dthumb-phinf.pstatic.net/?src=%22https%3A%2F%2Fssl.pstatic.net%2Fimages.se2%2Fsmedit%2F2015%2F10%2F7%2Fifgkjounjhek20.jpg%22&type=w2)이 된다.



#### 여기서 

 Strassen 이라는분이 1960년대 후반 
$$
O(n^3)
$$
보다 작은 알고리즘을 제시하게된다 .  


$$
O(n^3)
$$
의 속도가 깨지지 않을 것이라 생각했는데 

이보다 작은 시간이 나왔다는 것이 놀라운 이유이다.

현재도 Strassen Algorithm보다 더 빠른 알고리즘이 몇 나왔지만 성

능차이가 크지 않다 . 슈트라센 알고리즘의 시간복잡도는 기존보다 

더 낮은 
$$
O(n^{2.81})
$$
로 줄어들었지만 O-Notation 상의 속도는 더 빠르나, 

 Starssen Algorithm은 재귀적으로 돌려 시간이 오래걸리며, 반복적

 알고리즘으로 바꾸는데 어렵다. 또스트라센의 경우 행렬의 곱셉을

 하기 위해서는 정사각행렬에 대해서만 처리가 가능하다. 그렇지 않

을 경우에는 행렬을 정사각 행렬로 변경하는 작업이 필요하다



분할 정복알고리즘과 동일하고 예를들어 M에서는 각 행렬을 작은

 단위로 분할하며 최종 행렬을 구하기 위해서는 분할된 원소를 재조

립하는 과정으로 최종 행렬을 얻어낼 수 있다. 



![img](https://t1.daumcdn.net/cfile/tistory/2456D9395510C34428)



###### n이 2일경우 일반행렬곱이랑 별 다를바가 없다 

출처: https://loveisaround.tistory.com/entry/알고리즘-스트라센-strassen [언제나 밝음]

출처 :http://yimoyimo.tk/Strassen/

출처 : 위키백과

