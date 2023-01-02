Day 4 - Java 문법
---
Java 언어의 기본문법에 대해 보고서를 제출하세요

+ 프로그래밍 기초 문법
+ 예외 처리
+ 상속
+ 추상 클래스
+ 인터페이스

📚Java 프로그래밍 기초 문법
---

🔖KEYWORDS

🔖OOP - 객체 지향 프로그래밍


Keywords
---
미리 예약되어 있는 기능을 실행시켜주는 것으로, 자바라는 언어를 하기 위해 필요한 기본적인 단어

📎링크 참조: [All 50 Java Keywords](https://github.com/Suryakant-Bharti/Important-Java-Concepts/tree/master/_moreReadMe/keywords)

자바의 키워드는 총 50개이고, 그 중 2개는 더 이상 쓰이지 않아 실질적으론 48개의 키워드가 있다

🔎자주 사용하는 키워드 예시

```
⚙️class  //자바 프로그램의 최소 단위, 객체를 생성할 때 그 객체가 어떤 데이터를 갖고 어떤 연산을 하는지 정의해줌
⚙️package  //하나의 폴더(디렉토리)로서 여러 클래스가 모여있고 이를 통해 추가적인 작업이나 기능을 가능케 해줌
⚙️import  //다른 패키지의 이용을 쉽게 만들어주는 키워드로 그 패키지가 가진 기능들을 도입해줌 
⚙️public  //접근 제한자로 다른 패키지에 있는 클래스 및 클래스 자원을 사용할 수 있게 하는 역할
...
```

OOP - 객체 지향 프로그래밍 (Object Oriented Programming)
---
클래스와 객체들을 사용하는 패러다임과 방법론으로 소프트웨어 개발과 유지를 용이하게 만듦

+ Abstraction  //복잡한 자료와 모듈, 시스템에서 핵심이 되는 개념이나 기능을 위주로 간추려 편의성을 높임
+ Encapsulation  //외부의 접근을 제한시켜 정보 보호를 해주고 객체가 손상되지 않게 해줌
+ Inheritance  //클래스의 기능을 확장시킬 때 기존의 기능과 새로운 기능을 추가시켜주며 중복도 방지해줌
+ Polymorphism  //위의 추가된 기능들을 정확한 클래스에 맞게 재정의하여 기능성을 높여줌

👨‍🏫Java는 정해진 예약어와 내가 지정해준 객체들로 하나의 컴퓨터 언어를 만들어 사용할 수 있게 해주는 언어


Variables & Function (변수, 함수)
---

⚙️Variables 변수

변수란 데이터를 저장하기 위해 이름을 받은 메모리 공간을 의미하며, 이렇게 저장된 값은 변경될 수 있습니다

+ 변수의 이름 생성 규칙

```
1. 변수의 이름은 영문자, 숫자, 언더스코어, $로만 구성할 수 있다
2. 변수의 이름은 숫자로 시작할 수 없다
3. 변수의 이름 사이에는 공백을 포함할 수 없다
4. 변수의 이름으로 자바에서 미리 정의된 키워드는 사용할 수 없다
```

+ 변수의 종류

```
1. 기본형 변수
1-1. 정수 : byte, short, int, long 
1-2. 실수 : float, double
1-3. 문자 : char
1-3. 논리 : boolean


2. 참조형 변수
위의 기본형 변수를 제외한 모든 변수
```

⚙️Function 함수

특정 기능이나 작업을 수행하는 일련의 코드로 코드의 가독성과 재사용성을 높일 수 있음

+ 함수의 구성 요소

```
Header  //이름과 매개변수
Body  //함수의 동작 과정과 반환 값 등

# public class FunctionExample {
#         public static add(int num1, int num2){  //이름과 매개변수 부여, Header
#             int = result = num1 + num2;  //동작, 어떤 작업을 할 것인지 Body
#             return result;  //결과, 값 반환 Body
#             }
#         }
```

Operators 연산자
---
여러 종류의 연산을 수행하기 위한 것으로 간단히 입력함으로서 특정 기능을 수행

종류|연산자|우선순위
---|---|---
증감 연산자|```++, --```|1순위
산술 연산자|```+, -, *, /, %```|2순위
시프트 연산자|```	>>, <<, >>>```|3순위
비교 연산자|```>, <. >=, <=, ==, !=```|4순위
비트 연산자|```&, |, ^, ~```|~는 1순위, 나머지 5순위
논리 연산자|```&&, ||, !```|!만 1순위, 나머지 6순위
조건(삼항) 연산자|```?, :```|7순위
대입 연산자|```=, *=, /=, %=, +=, -=```|8순위

## 📎참고링크 : [연산자 세부 정보](https://phantom.tistory.com/19)


📚Exception Handling, 예외 처리
---
프로그램에 문제가 발생했을 때 시스템 동작에 문제가 없도록 사전에 예방하는 코드를 작성하는 방법

+ try, catch
+ finally
+ RuntimeException
+ Exception
+ throws
+ transaction

### ⚙️try, catch
가장 기본적인 예외 처리 방법

💻실습 코드

```
# try {
#   } catch(예외해결방안1) {
#   } catch(에외해결방안2)
# ...

이와 같은 구조로 try중 예외가 발생한다면 catch 구문 안에 있는 해결 방법이 이루어져 예외를 해결해준다
```

### ⚙️finally
예외가 발생해도 강제로 실행이 필요한 경우에 사용하는 처리 방법

💻실습 코드

```
# public class Sample {
#     public void mustRun() {
#         System.out.println("finally, it worked");
#     }

#     public static void main(String[] args) {
#         Sample sample = new Sample();
#         int c;
#         try {
#             c = 3 / 0;
#             sample.mustRun();  // 이 코드는 실행되지 않는다.
#         } catch (ArithmeticException e) {
#             c = -1;
#         }
#     }
# }

//위의 예시는 밑의 3을 0으로 나누는 불가능한 상황 (에러코드 ArithmeticException e) 때문에 실행이 불가
#         try {
#             c = 4 / 0;

//이때 finally를 이용하여 catch 밑에 함수를 작성해주면
#         } finally {
#             sample.shouldBeRun();  
// 예외에 상관없이 무조건 수행되어, "finally, it worked"라는 문장이 자동으로 출력된다
```

## 📎참고링크 : [이외 예외 처리 참고](https://wikidocs.net/229)


📚Inheritance, 상속
---
하위 클래스(자식)이 상위 클래스(부모)에게서 원하는 속성을 받아오는 것

⚙️상속은 ```extends``` 키워드를 사용, 상속을 받아 함수를 재정의 할 때는 @Override를 사용하여 재정의함을 명시

💻실습 코드

```
기본 방식
# class 자식클래스 extends 부모클래스 {
#       "필드 입력"
#       "생성자 입력"
#       "매서드 입력"
# }
```

```
상속 예제
# class Animal {
#    public void move() {
#       System.out.println("Animals can move");
#    }
# }

# class Dog extends Animal {
#    public void move() {
#       System.out.println("Dogs can walk and run");
#    }
# }

# public class TestDog {

#    public static void main(String args[]) {
#       Animal a = new Animal();   // Animal reference and object
#       Animal b = new Dog();   // Animal reference but Dog object

#       a.move();   // runs the method in Animal class
#       b.move();   // runs the method in Dog class
#    }
# }
```

## ⚠️Overriding, Overloading

⚙️Overriding : 하위 클래스에서 작업 중 상위 클래스를 재정의 하는 것

  메서드의 내용만 재작성 하는 것이므로, 혹여 잘못된 경로로 빠질 일이 없게 내용을 제외한 이름, 반환형, 변수와 관련된 모든 것은 동일해야 함
  
⚙️Overloading : 메서드의 이름은 같지만 변수의 갯수나 타입이 다른 경우에 사용

  같은 기능을 하는 메서드의 이름을 바꾸지 않고 다양하게 사용이 가능하며, 새로운 이름을 지어줄 필요가 없어서 편의성을 챙길 수 있음
  


📚Abstraction 추상 클래스
---
클래스를 이용하면서 멤버 변수를 갖기 위해 사용하는 것으로, 미리 만들어진 툴을 내게 필요한 부분만 바꾸어서 필요한 부분만 상속 받는 것

때문에 ```멤버 변수```를 가지며, 선언부는 갖고 있으나 구현부는 채워넣을 수 있게 작성이 되어 있지 않다 


⚙️How it works

```
# abstract 반환타입 메소드이름();
// 구현부가 없기 때문에 끝에 세미 클론이 추가된다

# abstract class Bike{  
#       abstract void run();  
# }  

💻실습 코드

# class Honda4 extends Bike{  
#       void run(){System.out.println("running safely..");}  
#         public static void main(String args[]){  
#           Bike obj = new Honda4();  
#               obj.run();  
#     }  
# }  
```

📚Interface 인터페이스
---
다중 상속을 가능하게 해주며 기본적인 베이스를 만들어주고, 다른 클래스들과의 중간 매개 역할을 담당하는 추상 클래스

+ 다중 상속을 사용하게 될 경우 데이터의 안정성이 위협받고 오류가 생길 확률이 높아지기 때문에 자바에서는 다중상속을 지원하지 않는다
+ 다중 상속이 필요한 경우에 새로운 추상 클래스, 인터페이스를 만들어 활용하는 것

⚙️How it works

```
키워드 ```interface```를 사용해 선언, 클래스를 만들면 .class라는 추상 클래스가 만들어진다


# 접근제어자 interface 인터페이스이름 {
#     public static final 타입 상수이름 = 값;
#       public abstract 메소드이름(매개변수목록);
# }

💻실습 코드

# interface printable{  
#     void print();  
# }  

# class A6 implements printable{  
#     public void print(){System.out.println("Hello");}  
#   
#       public static void main(String args[]){  
#           A6 obj = new A6();  
#           obj.print();  
#  }  
# }  
```

## 📎참고링크 [자바 개념](http://www.tcpschool.com/java/intro), [자바 개념 및 예제 참고](https://github.com/Suryakant-Bharti/Important-Java-Concepts)
