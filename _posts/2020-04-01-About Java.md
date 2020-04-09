---
layout: single

title: "About Java"

categories : Java version

tags : Java

date : "2020-04-01"
---









# Java 버전별 특징

Java가 빠르게 릴리즈 함에 따라 한번 짚어보고 가야할 필요를 느껴서 Java 7~10까지 버전별 특징들을 정리해보았습니다.

# 1. Java 7

## 1.1 Type Inference (타입 추론)

```
// 7 버전 이전
List<String> list = new ArrayList<String>();

//7 버전 이후
List<String> list2 = new ArrayList<>();
```

## 1.2 Switch 문 문자열 case

- 말 그대로 Switch ~ Case 문에 문자열이 가능해졌다.
- 어떤 식으로 컴파일하는지 궁금해서 직접해보았다.(~~이렇게 String을 지원하기까지 약 16년이 걸렸다는..~~)

```
// Java 코드
switch (a) {
    case "jeongmin":
        System.out.println("asd");
        break;
    case "jeongmin2":
        System.out.println("qweqwe");
        break;
    default:
        break;
}
// 컴파일 후 .class 파일(Java 8 기준)
byte var4 = -1;
switch(a.hashCode()) {
case -1514507291:
    if (a.equals("jeongmin")) {
        var4 = 0;
    }
    break;
case 294914285:
    if (a.equals("jeongmin2")) {
        var4 = 1;
    }
}

switch(var4) {
case 0:
    System.out.println("asd");
    break;
case 1:
    System.out.println("qweqwe");
}
```

- 첫번째 switch ~ case의 String 값을 hashcode 값 변경하고, equals 메소드를 통해서 실제 값과 같은지 다시 비교하고있다.
- 그렇게 hashcode를 기준으로 초기화 된 `var4`라는 변수를 이용하여 두번째 switch ~ case 문에서 실질적인 동작을 하게 된다.
- 

- 사실 ‘hashcode로 바로 case문을 적용하면 되지않을까?’라는 생각을 할 수 있지만 hashcode라는게 다른 객체끼리 hash 충돌이 나게되면 중복될 수 있기 때문에 두번에 걸쳐서 검사를 한다고 한다.

## 1.3 Automatic Resource Management

- 보통 DB연동이나 파일스트림 같이 open하고 close를 해주어야하는 경우 try ~ catch문 다음에 finally에 close를 해주게 되는데 7부터는 finally에 close를 쓰지않게되면 알아서 try 마지막에 close 하게된다.

## 1.4 Catching Multiple Exception Type in Single Catch Block

- 7 이후부터 멀티 catch가 가능해졌다.

## 이진수 표현

- 숫자 앞에 0B나 0b를 붙이면 이진수로 판단 (8진수는 0, 16진수는 0x, 0X)

# 2. Java 8

## 2.1 Lambda

- Lambda 표현식 이라고 불리며, 다양한 표현식이 있다. (다양한 표현방식이 존재해서 다음에 따로 다시 정리할 것)
- 람다표현식은 컴파일러(JIT 인터프리터)한테 실질적 구현을 시키는 방식이다.
- 단순 for-loop와의 비교를 하게되면 람다표현식을 사용하면 더 느릴 수도 있지만 무조건적인 것은 아니라고한다. [참고 링크](https://brunch.co.kr/@heracul/3)

## 2.2 interface 클래스에 구현체 작성 가능

- default와 static 키워드를 사용해서 구현 메소드를 interface에 작성할 수 있게 되었다.

## 2.3 Optional

- Optional은 `null이 될 수도 있는 객체`를 감싸는 일종의 래퍼 클래스이다.
- 2019 SpringCamp에서도 세션으로 나왔을 만큼 null 다루는 것은 상당히 까다롭고, NPE 에러 또한 상당히 많이 나오는 에러이다.
- 하지만, null체크를 최대한 하지않고도 코딩하게끔 나온 클래스이므로 사용을 잘해야한다. [참고](http://www.daleseo.com/java8-optional-effective/)

## 2.4 다양한 DateTime 추가 (LocalDateTime, …)

## 2.5 GC 성능 대폭 개선

- Java 8부터는 메모리 누수를 일으키던 메소드 영역의 PermGen Area를 제거하여 static 인스턴스와 리터럴 문자열도 GC의 대상이 되도록 바뀌었으며, 클래스, 메소드,배열의 메타 정보는 동적 리사이징이 가능한 Metaspace로 이동시켜 시스템 힙 영역에 저장된다. 덕분에 JVM 힙 영역의 공간이 늘어나고 PermGen Area를 스캔/삭제할 필요가 없어져 GC의 성능이 대폭 향상되었다.

# 3. Java 9

## 인터페이스 내에 private 구현체 가능

## 모듈시스템 등장(jigsaw)

- 기존 jar방식을 개선하기위해 등장함

# 4. Java 10

- Local Variable Type Inference → var 사용
- JVM heap 영역을 NVDIMM (비휘발성 NAND 플래시 메모리) 혹은 사용자 지정과 같은 대체 메모리 장치에 할당 가능



출처 : https://ggomi.github.io/jdk-version/

