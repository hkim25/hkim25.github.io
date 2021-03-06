---
layout: post
title: Spring 웹개발자 기술면접 준비
date: 2021-10-11
author: HongJoong Kim
categories: 개념정리
tags: [javascript,java,spring,sql]
---

## 서론

면접이 코 앞으로 다가왔다. 인터넷에서 예상질문 등 관련자료를 찾던 도중 잘 정리된 블로그 게시물을 발견했고, 이 글을 쭉 훑어본 후 정리된 항목 및 키워드만 가져와서 내가 알고있는대로 다시 답해보았다.<br>
이후 블로그 원글 내용과 비교하며 미흡한 부분을 더 찾아보는 식으로 면접을 준비하려 한다. 

> <a href="https://minchoi0912.tistory.com/93" target="_blank">https://minchoi0912.tistory.com/93</a>

<br>

## JAVA

__OOP(객체 지향 프로그래밍)이란?__  
모든 것을 객체화 시켜서 프로그래밍 하는 기법. 실제 세상과 비슷한 구조로 짜이게 되어 직관적으로 이해하기 쉽고 코드의 재사용성이 올라간다는 장점. java에서는 class와 instance를 통해 객체화를 진행.

<span style="color:Tan">객체와 객체의 유기적인 상호작용을 통해 프로그램이 작동하는 것. 여기서 객체란 현실의 물체를 의미함. 사람의 사고와 가장 비슷하게 프로그래밍 가능 함. 하나의 클래스를 바탕으로 서로 다른 상태의 인스턴스를 만들면서 다른 행동들을 하게 할 수 있음. = 코드의 재사용 가능(재활용성), 유지 보수에 용이함.  
반대) 절차지향 : 순차적인 처리 중시, 프로그램 전체가 유기적으로 연결. C언어. 컴퓨터 작업 처리 방식과 유사함.</span>
  
<span style="color:IndianRed">객체와 객체의 유기적인 상호작용, 사람의 사고와 비슷한 프로그래밍, 반대개념은 절차지향이라는걸 기억해 둘 것  </span>
  
__자바의 장단점__  
장점 개발단계부터 객체지향 언어. 객체지향 프로그래밍에 적합. 모듈화를 통해 재사용성이 높다.캡슐화를 통해 높은 보안성. JVM 상에서 가동되기 때문에 OS를 가리지 않고 호환성이 좋음.  
단점 느림. 상대적으로 low-level 언어라 배우기 힘듦.

<span style="color:Tan">장점 자바 가상 머신 위에서 동작하기 때문에 OS에 독립적임. 아파치, 스프링과 같은 자바를 지원하는 많은 오픈 소스 프로젝트가 존재하여 짧은 개발 시간 내에 안정적인 프로그램 구현 가능.  
단점 비교적 속도가 느림. 하드웨어 성능의 발전으로 JVM 기능이 향상되어 격차가 많이 줄어들었음.</span> 

<span style="color:IndianRed">이대로 괜찮은듯</span>

__메모리영역__  
메소드영역, stack, heap으로 구성  
메소드 영역 : 모르겠어  
Stack : 기본형 변수의 값과 클래스 등이 저장되는 영역  
Heap : 참조형 변수의 값과 인스턴스 등이 저장되는 영역. 휘발성이 가장 강하다.

<span style="color:Tan">메소드 영역 : static 변수, 전역변수, class정보들 저장.  
stack : 지역변수, 메서드 등이 할당  
heap : new 연산자를 통한 동적 할당된 객체 저장. 가비지 컬렉션에 의해 관리.</span> 

<span style="color:IndianRed">메소드영역에는 static 변수와 전역변수, class 정보들이 저장된다. 클래스 스택 아님! 지역변수와 메서드가 스택  </span>


__기본형 자료, 참조형 자료__  
기본형 자료 : int, Boolean 등 원시 자료형. 변수 자체에 값이 들어감. Stack 영역에 저장됨  
참조형 자료 : 변수에 들어가는 데이터는 값이 아니라 주소. Heap 영역에 메모리를 생성해 값을 저장하고 그 주소를 변수에 저장함.

<span style="color:Tan">기본형(primitive) : stack 메모리 영역에 실제 값을 저장하는 데이터 타입. byte, short, int, long, float, double, char, boolean / call by value 호출 방식을 사용함.  
참조형(reference) : 메모리 상에 객체가 있는 위치를 저장하는 것. String, 클래스, 인터페이스 등. new 연산자로 정의. 실제 값은 heap에 저장되고 stack에는 메모리 주소만 저장. call by reference.</span> 

<span style="color:IndianRed">문제없음</span>

__가비지컬렉션이란?__  
Heap 영역에서 더 이상 사용하지 않는 (아무도 참조하지 않는) 데이터는 가비지컬렉터가 순찰하며 지워버림. 리소스 관리를 위해 필요한 작업.  
JAVA에선 알아서 하기 떄문에 신경 안써도 됨.

<span style="color:Tan">시스템에서 더 이상 사용하지 않는 동적 할당된 메모리 블록을 찾아 다시 사용한 자원으로 회수하는 것. 자동으로 이루어지므로 메모리 영역 관리 할 필요 없음.</span>

<span style="color:IndianRed">동적 할당된 메모리 블록이라는 표현 기억해둘 것.</span>

__전역변수와 지역변수__  
클래스 전체에서 참조할 수 있는 변수는 전역변수. 특정 메소드 안에 선언한 변수는 지역변수가 되어 그 메소드 안에서만 사용할 수 있다.

<span style="color:Tan">전역변수 : 함수 바깥에 선언하여 클래스 전체에서 사용 가능한 변수. 여러 메소드에서 공통적으로 사용 가능.  
지역변수 : 함수 속에서 선언하여 해당 함수 속에서만 사용 가능한 변수.</span>

<span style="color:IndianRed">문제없음</span>

__Static의 의미__  
정적이라는 의미의 키워드. 최초 메서드영역 메모리를 생성할 때 같이 생성되며 절대 변하지 않는다. 변수가 아닌 상수가 됨.

<span style="color:Tan">메모리 공간 할당 시 처음 설정된 메모리 공간이 변하지 않는 것. 객체를 생성하지 않고도 사용할 수 있는 필드와 메소드. 객체마다 가지고 있을 필요가 없는 공용적인 데이터라면 static으로 선언. 객체 생성을 하지 않고 사용 가능하기 때문에 인스턴스 필드, 메소드를 내부에서 사용 할 수 없음.</span>

<span style="color:IndianRed">설명 보고 생각났는데 객체 클래스 내 static으로 생성한 변수는 클래스변수라고 부르며 인스턴스 없이 클래스 이름으로 바로 접근 가능함  </span>

__String, StringBuffer, StringBuilder__  
String 데이터가 수정될 때 heap 영역에 새로운 데이터를 생성해 참조 주소를 바꿈.  
StringBuffer 주소를 그대로 두고 데이터 자체를 바꿈. 수정이 빈번히 일어날 때 유리  
StringBuilder 버퍼랑 똑같은데 동기화가 안되어서 멀티쓰레드 환경에 불리하다고 함. 뭔소린지 모르겠음.

<span style="color:Tan">String은 new 연산자를 통해 생성되면 인스턴스 메모리 공간이 절대 변하지 않으므로 +, concat과 같은 연산시 메모리의 내용이 변하는 것이 아니라 새로운 String 인스턴스가 생성됨. 이렇게 새로운 문자열이 만들어지면 기본의 문자열은 가비지 콜렉터에 의해 제거되야 함. 문자열 연산이 많아지는 경우 성능이 떨어짐. 하지만 불변하기 때문에 조회가 빠르고 멀티스레드 환경에서 동기화를 신경 쓸 필요 없음.  
StringBuffer와 StringBuilder는 String과 다르게 클래스는 한 번만 만들고 메모리의 값을 변경시켜서 문자열을 변경함. 그러므로 문자열 연산이 자주 있을 때 사용하면 좋음.  
StringBuffer은 멀티 스레드 환경에서 synchronize 키워드가 가능하므로 동기화가 가능하다. StringBuilder는 동기화를 지원하지 않기 때문에 멀티 스레드 환경에서 적합하지 않음.</span> 

<span style="color:IndianRed">이해한건 대강 맞음. 그냥 그런가보다 하자.</span>

__접근제한자__  
Default 모르겟숴요  
private 해당 클래스 내에서만 접근가능. 외부에서 접근하려면 게터,세터 메소드 필요  
protected 같은 패키지 내에서 접근 가능, 다른 패키지에서는 해당 클래스의 자식클래스인 경우 접근 가능.  
Public 어디서나 접근 가능

<span style="color:Tan">public : 모든 클래스 접근 가능  
protected : 같은 패키지, 해당 클래스를 상속받은 외부 패키지의 클래스  
default : 같은 패키지에서만 접근 가능  
private : 같은 클래스에서만 접근 가능</span>

<span style="color:IndianRed">dafault는 같은 패키지에서만 접근 가능!</span>

__객체란 무엇인가__  
모든 것은 객체다. 

<span style="color:Tan">우리 주위의 모든 데이터와 기능을 가진 것들이 객체가 될 수 있음.  
ex) 식당에서 주문의 과정에서 종업원, 손님, 주문서, 메뉴판</span>  

<span style="color:IndianRed">데이터와 기능을 가진 모든 것들은 객체가 될 수 있다. 표현 기억해둘 것.</span>

__클래스와 인스턴스__  
객체화된 무언가가 클래스. 그 클래스를 기반으로 만들어진 데이터가 인스턴스.

<span style="color:Tan">클래스란? 설계도. 클래스를 통해서 인스턴스 객체 생성 가능.  
인스턴스 : 객체가 메모리에 할당되어 실제 메모리를 차지 하는 것.</span>

<span style="color:IndianRed">설계도라는 표현 기억.</span>

__추상클래스__  
추상메소드를 하나 이상 갖고 있는 클래스는 추상클래스가 되어야 한다.  
추상메소드? 구현부가 비어있는 메소드 -> 상속받은 니가 알아서 채워라  
추상클래스를 쓰는 이유? 추상메소드의 구현부를 반드시 구현하도록 강제하기 위함.  
그럼 추상화를 왜 함? 중복되는 코드를 줄이기 위해. 재사용성, 다형성


<span style="color:Tan">추상 메소드를 하나 이상 가진 클래스
자식 클래스에게 강제성 부여 가능. 이를 통해서 기능 확장 가능.  
직접적으로 객체 생성이 불가능하고 클래스를 상속 받아서 오버라이딩하여 사용해야 함.</span>

<span style="color:IndianRed">강제성 기억. 추상클래스로 인스턴스 못만드는 것 기억.</span>


__인터페이스__  
모든 메소드가 추상메소드인 깡통 클래스
협업에 유리. 메소드 안쪽이 어떻게 생겼는지 몰라도 이름만 알면 갖다 쓸 수 있음.

<span style="color:Tan">모든 메서드가 구현부가 없는 추상메서드로 이루어진 클래스</span>
<span style="color:Tan">ex) 키보드. 키보드를 누른다 라는 행위는 같지만 엔터/스페이스바를 눌렀을 때의 결과는 다름. 메소드는 같지만 동작 방식은 다르게 다형성을 주고 싶은 경우 사용.  
협업시 객체의 내부 구조를 모르더라도 인터페이스의 메서드 명만 알면 사용 가능 = 협업에 유리.  
interface, implements, abstract pubilc 메소드, public static final 상수  
다중 구현 가능.</span>

<span style="color:IndianRed">문제없음</span>

__추상클래스와 인터페이스의 차이점__  
목적이 다름.  
인터페이스는 여러 사람이 쓰기 쉽게 하라고 구현부를 비움.   
추상클래스의 추상메소드는 오버라이딩을 통해 중복되는 코드를 줄이기 위해서.

<span style="color:Tan">목적이 다름.  
추상 클래스는 추상 메서드를 자식 클레스가 구체화해서 기능 확장에 목적이 있지만 인터페이스는 서로 관련이 없는 클래스에서 공통적으로 사용하는 방식이 필요하지만 기능은 각각 구현해야 하는 경우에 사용.  
추상 클래스는 단일 상속, 인터페이스는 다중 구현 가능.</span>

<span style="color:IndianRed">추상클래스 : 기능확장, 인터페이스 : 방식은 같지만 기능을 각각 구현하기 위해.</span>

__오버라이딩, 오버로딩__  
오버라이딩 부모클래스에 이미 존재하는 메소드를 상속받은 자식클래스에서 덮어 쓸 수 있는 기능.  
코드가 불필요하게 복잡해지는걸 막아줌. 메소드 호출시 자식클래스에서부터 해당 메소드가 있는지 찾아보고 없다면 위로 거슬러 올라감.  
오버로딩 파라미터의 숫자나 타입이 다르다면 이름이 같아도 다른 메소드로 취급하는 것. 메소드를 호출할 때 기억해야 할 이름이 줄어들기 때문에 편리하다.

<span style="color:Tan">오버라이딩이란 상속에서 나온 개념. 부모 클래스의 메소드를 자식 클래스의 메소드로 재정의 하는 것. 기능의 확장을 위해서 사용 함.  
오버로딩이란 같은 클래스 내에서 같은 이름의 메소드를 여러개 정의 하는 것으로 매개변수의 타입이 다르거나 개수가 다름. return 타입과 접근 제한자는 영향 없음.</span>

<span style="color:IndianRed">문제없음</span>

__다형성__  
오버라이딩과 오버로딩이 갖고 있는 특성. Java는 다형성을 가진 언어이다.

<span style="color:Tan">하나의 클래스나 함수가 다양한 방식으로 동작 가능 한 것. 오버라이딩과 오버로딩을 통해서 다형성 구현 가능.  
ex) 게임 > 다양한 캐릭터들에 대해서 동일한 버튼을 클릭해서 다른 스킬을 사용하게 하는 것.</span>

<span style="color:IndianRed">하나의 클래스나 함수가 다양한 방식으로 동작 가능한 것. 표현 깔끔하다.</span>

__상속__  
부모클래스의 모든 요소를 자식클래스에 물려주는 것. 중복되는 코드를 줄이기 위해 사용한다.

<span style="color:Tan">부모 클래스가 가지고 있는 상수, 메소드를 자식 클래스에서 물려 받아 같이 공유하면서 확장하는 것  
자식 클래스의 부모 클래스 메소드 재정의 > 오버라이딩  
코드 중복 방지, 공통적인 코드 변경 할 때 시간 단축 가능.</span>

<span style="color:IndianRed">문제없음</span>

__쓰레드__  
프로세스가 처리되는 단위라고 들었는데 대충 넘겨서 정확히 모르겠다…

<span style="color:Tan">프로세스 내에서 실제로 작업을 수행하는 주체를 의미하며 모든 프로세스에는 한 개 이상의 스레드가 존재하여 작업을 수행함. 두개 이상 스레드를 가지는 프로세스를 멀티 스레드 프로세스라고 함.  
Thread 클래스, Runnable 인터페이스를 통해 구현 가능  
장점 : 빠른 프로세스 생성 가능, 정보 쉽게 공유 가능.  
단점 : 교착 상태 : 다중 프로그래밍 체제에서 하나 또는 그 이상의 프로세스가 수행 할 수 없는 어떤 특정 시간을 기다리고 있는 상태.</span>

<span style="color:IndianRed">봐도 모르겠네</span>

__JDBC__  
Java와 각종 DMBS를 연결하여 작업하기 위한 java api. 여러 개의 클래스로 구성되어 있으며 java 파일에 직접 query를 작성하여 입력해야 함.

<span style="color:Tan">자바에서 DB의 종류에 상관 없이 데이터베이스에 더욱 쉽게 접근 할 수 있도록 하는 API.  
Connection, PreparedStatement, ResultSet 등 여러개의 클래스를 생성하고 Exception 처리도 해야 하는 번거로움이 있음 > 반복적인 코드 발생, 생산성 저하.  
Spring JDBC : 기존의 JDBC 단점 극복, 반복적으로 해야 하는 많은 작업들을 대신 해줌. Connection 열기 닫기, Statement 준비, 실행
ConnectionPool : DB와 항상 연결되어 있는 객체들. DB와의 연결을 위해서 사용하는 객체
DataSource : ConnectionPool 관리 객체. 커넥션풀 이용해서 연결, 반납하는 작업 수행.
pom.xml에서 dependency 추가</span>

<span style="color:IndianRed">문제없음</span>

__싱글톤 패턴__  
하나의 클래스가 하나의 인스턴스만 갖고 있는 형태.

<span style="color:Tan">하나의 클래스에 대해 하나의 인스턴스만 만들어서 사용하기 위한 패턴. 커넥션 풀과 같은 객체의 경우 인스턴스를 여러개 만들게 되면 자원 낭비가 되므로 하나만 생성하는 것이 효율적.  
생성자에 private 접근 제어자를 지정해 인스턴스 생성에 제약을 걸고, 단일 객체를 반환 할 수 있도록 정적 메소드를 지원해야 함.</span>

<span style="color:IndianRed">자원 낭비를 방지하기 위해 사용함</span>

__직렬화__  
모르겟숴요  

<span style="color:Tan"><https://ktko.tistory.com/entry/개발자-면접-질문자바-스프링?category=625364></span>

<span style="color:IndianRed">저쪽 글도 쭉 읽어봅시다.</span>

__제네릭__  
`Collection<DataType>` 형태로 사용하며 컬렉션에 들어갈 데이터 타입을 미리 정해주는 것. 오류 발생 확률을 줄이기 위해 사용한다.

<span style="color:Tan">클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법.  
코드의 안정성과 재사용성을 높여줌 > 객체 타입을 컴파일 시에 체크하고, 형변환을 하지 않아도 됨.</span>

<span style="color:IndianRed">문제없음</span>

__컬렉션__  
Map key, value 형태로 저장. 순서 없음, key값 중복 불가.
Set 중복 불가, 순서 없음
List 중복 허용, 순서 있음

<span style="color:Tan">다수의 데이터를 다루는데 표준화된 클래스들을 자료구조를 직접 구현하지 않고 편하게 사용 가능 함.  
배열과 다르게 객체를 보관하기 위한 공간을 미리 정의하지 않아도 됨 > 객체의 수를 동적으로 할당 가능하므로 효율성 증대.  
List, Set, Map (인터페이스)  
List : 순서 있는 데이터의 집합. 데이터의 중복 허용.  
ArrayList : 단방향 포인터 구조. 각 데이터에 대한 인덱스를 가짐. 검색에 적합. 삽입, 삭제시 데이터 이후 모든 데이터가 복사 됨으로 빈번한 경우에는 부적합.  
LinkedList : 양방향 포인터 구조. 데이터의 삽입, 삭제시 해당 노드의 주소지만 바꾸면 되므로 삽입, 삭제가 빈번한 데이터에 적합. 처음부터 노드 순회하므로 검색에는 부적합.  
Set : 순서를 유지하지 않는 데이터 집합. 데이터 중복 허용하지 않음.  
HashSet :  
TreeSet ;  
Map : Key와 value의 쌍으로 이루어진 데이터 집합. 키는 중복을 허용하지 않고 순서를 유지하지 않음.  
HashMap  
containsKey / containsValue : key와 value가 포함되어 있는지 알려준다.  
put : key, value 형태로 set에 저장함.  
get : 지정된 key값을 반환함.  
size() : 개수 반환</span>

<span style="color:IndianRed">문제없음</span>

__==와 .equals()의 차이__  
==는 참조하는 주소가 같은지 비교
.equlas()는 참조한 값 자체를 비교

<span style="color:Tan">== : 주소 값 비교  
equals : 내용 비교</span>

<span style="color:IndianRed">문제없음</span>

__length, length(), size()__  
length – 배열의 요소 (배열 크기가 저장됨)  
length() – String의 메서드 (문자열 길이 리턴)  
size() – List의 메서드 (배열 크기 리턴)

<span style="color:Tan">length : 배열 / length() : 문자열 길이 / size() : 컬렉션 프레임워크(arraylist) 타입의 길이</span>

<span style="color:IndianRed">문제없음</span>

__JDK__  
자바 개발자 도구. 개발하려면 jre 말고 이걸 깔아야 함(jre포함됨)

<span style="color:Tan">JDK (Java Developmnet Kit) : 자바 프로그램 개발도구. 자바 애플리케이션을 구축하기 위한 핵심 플랫폼 구성 요소.</span>

<span style="color:IndianRed">문제없음</span>

## javascript

__jQuery__  
css 선택자 문법을 사용하여 DOM을 쉽게 선택하고 조작할 수 있는 자바스크립트 라이브러리

<span style="color:Tan">자바스크립트의 라이브러리로 자바스크립트를 조금 더 편리하게 사용하기 위한 언어.  
달러 표시를 이용해서 코드가 간결해짐.</span>
<span style="color:IndianRed">문제없음</span>

__부트스트랩__  
쉽고 빠른 반응형 웹 css 라이브러리. 태그 내 class 요소를 사용하여 컨트롤

<span style="color:Tan">_CSS를 다루는 프레임 워크</span>

<span style="color:IndianRed">문제없음</span>

__Ajax__  
비동기식 제이슨 앤드 엑스엠엘
비동기 방식으로 서버와 통신하여 데이터를 주고받는 기술. 가볍고 빠르다.
주고받는 데이터양식은 이름처럼 제이슨이나 xml 방식. jQuery로 Ajax를 사용하면 더 쉽다. 

<span style="color:Tan">자바스크립트의 라이브러리 중 하나.  
Asynchronous Javascript and XML (비동기식 자바스크립트와 XML)  
XMLHttpRequest  
전체 페이지를 새로 고치지 않고 페이지의 일부만을 위한 데이터를 로드하는 기법.  
자바스크립트를 이용한 비동기 통신, 클라이언트와 서버간에 Json 또는 XML 형태의 데이터를 주고받는 기술 > 자원과 시간을 아낄 수 있음.</span>

<span style="color:IndianRed">페이지의 일부만을 위한 데이터를 로드한다는 표현 좋다. 기억해둘 것.</span>

__Json__  
데이터를 표현하는 양식. 인간과 컴퓨터 모두 알아보기 쉽다는 장점이 있으며 무게가 가볍다. 관련 라이브러리도 많아 가공하기 편하다.

<span style="color:Tan">자바스크립트의 객체를 만드는 표현식으로 key, value로 이루어져 있음. 경량의 DATA를 교환하는 방식.</span>_

<span style="color:IndianRed">자바스크립트 객체를 만드는 표현식? 아님. 제이슨으로 자바스크립트 객체도 만들 수 있는거지 잘못된 표현.</span>
<span style="color:Maroon">위키백과 : JSON은 속성-값 쌍 또는 "키-값 쌍"으로 이루어진 데이터 오브젝트를 전달하기 위해 인간이 읽을 수 있는 텍스트를 사용하는 개방형 표준 포맷이다. 비동기 브라우저/서버 통신 을 위해, 넓게는 XML을 대체하는 주요 데이터 포맷이다.</span>

__동기, 비동기__  
서버와 신호를 주고 받을때마다 페이지를 다시 불러오는 방식이 동기.
페이지 리로딩 없이 데이터만 주고 받는 방식이 비동기.

<span style="color:Tan">동기 : A, B가 있다면 A를 수행하는 중에는 B를 수행하지 못하는 것을 의미함. 요청을 보낸 뒤 응답을 받아야지 다음 동작이 이루워짐. 설계가 간단하고 직관적이지만 시스템 전체적인 효율이 저하 된다.  
비동기 : A를 수행하면서 B를 수행하는 것. 동기 방식보다 복잡하지만 자원을 효율적으로 사용 할 수 있음.</span>

<span style="color:IndianRed">설명이 좀 이상해서 찾아봤는데 더 직관적인 설명을 찾았다.
동기(synchronous : 동시에 일어나는)  
동기는 말 그대로 동시에 일어난다는 뜻입니다. 요청과 그 결과가 동시에 일어난다는 약속인데요. 바로 요청을 하면 시간이 얼마가 걸리던지 요청한 자리에서 결과가 주어져야 합니다.  
요청과 결과가 한 자리에서 동시에 일어남  
A노드와 B노드 사이의 작업 처리 단위(transaction)를 동시에 맞추겠다.  
비동기(Asynchronous : 동시에 일어나지 않는)  
비동기는 동시에 일어나지 않는다를 의미합니다. 요청과 결과가 동시에 일어나지 않을거라는 약속입니다.   
요청한 그 자리에서 결과가 주어지지 않음  
노드 사이의 작업 처리 단위를 동시에 맞추지 않아도 된다.  
출처: <https://private.tistory.com/24> \[공부해서 남 주자\]</span>

__콜백함수__  
특정 코드가 모두 실행된 이후 다음 함수가 실행되는 방식으로 짠 함수.
여러 코드가 동시에 실행되어 순서가 꼬이는걸 막아줌.

<span style="color:Tan">어떤 특정 함수가 실행을 마친 뒤에 실행되는 함수.  
사용하는 이유 중 하나는 비동기 데이터를 처리하기 위함. 다른 함수의 실행이 끝날 때 까지 특정 코드가 실행되지 않게 기다려주는 방법.</span>

<span style="color:IndianRed">비동기 데이터를 처리할 때 콜백함수가 유용하다는 사실 기억.</span>

__이벤트루프__  
모르겟숴요

<span style="color:Tan">자바스크립트는 싱글 스레드로 그 자체로는 비동기 작업을 할 수 없지만, 웹 브라우저의 도움을 받아서 구현이 가능함. 이벤트 루프는 웹 브라우저에서 사용되는 기능 중 하나.</span>

<span style="color:IndianRed">웹 브라우저에서 사용되는 기능으로 자바스크립트만으로는 불가능한 비동기 작업을 할 수 있게 도와준다.</span>

__DOM__  
도큐먼트 오브젝트 엠….엠…..
아무튼 html 요소 하나하나를 객체화시켜 dom이라 부름

<span style="color:Tan">Document of Model의 약자.</span>

<span style="color:IndianRed">영어실력 참담하다. 도큐먼트 오브 모델이구나.</span>

__This__  
이 요소를 뜻하는 키워드. 어디서 어떻게 쓰느냐에 따라서 가리키는 값이 천차만별임.

<span style="color:Tan">this는 모든 함수 스코프 내에 자동으로 설정되는 특수한 식별자로 함수를 호출하는 방법에 의해 결정.</span>

<span style="color:IndianRed">문제없음</span>

__==와 ===의 차이점__  
==는 값만 비교, ===는 타입까지 비교

<span style="color:Tan">==은 값의 일치 여부만 확인하고 ===은 타입도 같이 확인함.</span>

<span style="color:IndianRed">문제없음</span>

## Database

__JOIN__  
원하는 데이터를 추출하기 위해 두 개 이상의 테이블을 합치는 일
INNER JOIN 교집합만 표시
RIGHT OUTER JOIN 오른쪽(나중에 적은) 테이블 컬럼 전부 표시, 안겹치는 COLLUMN은 NULL
LEFT OUTER JOIN 이건 왼쪽
FULL OUTER JOIN 양쪽 전부 다 표시. RIGHT OUTER JOIN UNION LEFT OUTER JOIN 하면 FULL OUTER JOIN 됨

<span style="color:Tan">2개 이상의 테이블을 연결하여 데이터를 검색하는 방법  
기본키, 외래키 값을 사용하여 조인한다.</span>

<span style="color:IndianRed">문제없음</span>

__데이터베이스 사용 이유__  
사용자에게 접근 및 수정 권한을 각각 다르게 부여함으로써 보안 유지
일관성 – 누가 뭐 하나 건드리면 나머지 사람들에게도 똑같이 바뀜

<span style="color:Tan">데이터의 보안성 > 인가된 사용자들만 데이터베이스, 데이터베이스 내의 자원에 접근 가능하도록 계정 관리 또는 접근 권한 설정  
데이터의 일관성 > 작업 중 일부 데이터만 변경되어 나머지 데이터와 일치하지 않는 불일치성 배제 가능  
데이터 중복 최소화 > 데이터를 통합해서 관리함으로써 자료의 중복과 데이터의 중복 문제 해결 가능_  

<span style="color:IndianRed">문제없음</span>

__정보, 데이터, 데이터베이스, 데이터베이스 관리시스템__  
정보 목적과 수단에 맞게 데이터를 가공한 것
데이터 단순히 수집된 원시 자료
데이터베이스 데이터가 저장되는 곳
데이터베이스 관리시스템 ORACLE, MySQL 등 데이터베이스를 관리하기 위한 시스템 및 프로그램

<span style="color:Tan">정리된게 없네요</span>

<span style="color:IndianRed">문제없음</span>

__SELECT FROM WHERE GROUP BY HAVING ORDER BY 처리 순서__  
from – where – group by – having – select - order by

<span style="color:Tan">select > from > where > group by > order by  
where ↔ having : having절은 그룹 함수의 그룹 조건, where 절은 select 할 데이터에 조건을 주는 역할</span>

<span style="color:IndianRed">이거 설명 잘못된 것 같은데?? where랑 having은 배타적이지 않아요</span>

__SQL이란?__  
에스..에스….스트럭…..구조적 쿼리 랭귀지
데이터베이스를 통제하기 위한 약속된 언어

<span style="color:Tan">데이터베이스의 질의에 사용되는 언어.</span>

<span style="color:IndianRed">스트럭쳐드!!!</span>

__DML, DDL, DCL__  
뭔지 아는데 가운데 글자가 안떠올라서 어디에 뭐가 들어가는지는 모르겟숴요
tcl인가도 있지 않냐 트랜잭션 컨트롤 랭귀진가 commit이랑 rollback
그럼 dcl은 데이터 컨트롤이겠네 insert, update, delete 들어감

<span style="color:Tan">DML (Data Manipulation Language) : 데이터베이스에 들어있는 데이터를 조작하는, 조회하거나 검색하기 위한 명령어. SELECT, UPDATE, INSERT, DELETE  
DDL (Data Definition Language) : 테이블 구조를 정의하는데 사용되는 명령어, CREATE, ALTER, DROP, TRUNCATE (초기화)  
DCL (Data Control Language) : 데이터베이스에 접근하거나 객체에 권한을 주는 등 역할을 하는 언어 commit, rolllback, grant, revoke</span>

<span style="color:IndianRed">여기는 문제가 많다. 다시 정리하고 기억해둘 것.  
DDL : definition. CREATE ALTER DROP TRUNCATE - TABLE 관련  
DML : manipulation. SELECT INSERT DELETE UPDATE - COLUMN 관련  
DCL : control. GRANT REVOKE - 권한 관련  
TCL : Transaction control. COMMIT ROLLBACK - 트랜잭션 관련</span>


__Commit__  
일정 트랜잭션을 마치고 변경사항을 저장하는 것

<span style="color:Tan">하나의 논리적 단위에 대한 작업이 성공적으로 끝났을 때 트랜잭션이 행한 갱신 연산이 완료된 것을 트랜잭션 관리자에게 알려주는 연산. DB에 변경 사항을 저장하는 것.</span>

<span style="color:IndianRed">문제없음</span>

__데이터 무결성__  
모르겟숴요…

<span style="color:Tan">개체 무결성 : 기본키는 Null 값이 올 수 없고 중복 될 수 없다.  
참조 무결성 : 외래키는 Nulll 값이 올 수 없고, 부모 테이블의 기본키에 종속 되어야 한다.</span>

<span style="color:IndianRed">아 ㅇㅋ 아는거임 당연하잖아 PRIMARY KEY FOREIGN KEY는 NOT NULL임  
이걸 개체 무결성, 참조 무결성이라고 부른다. 기억할 것.</span>

__인덱스__  
검색 기능을 향상시키기 위해 db 내부적으로 할당하는 목차값.

<span style="color:Tan">데이터를 정렬하여 검색과 정렬 작업의 속도를 높이기 위해 사용되는 것. 예를 들어서 책에서 가장 빨리 내용을 찾을 때 뒤편의 색인을 보면 된다.  
단점 : 데이터를 가져올 때 성능은 빨라지지만 데이터의 삽입, 변경등이 일어날 때 매번 인덱스가 변경되면 성능이 떨어질 수 있음 > 데이터 필터링을 사용 할 때 적합</span>

<span style="color:IndianRed">문제없음</span>

__정규화__  
Db 모델링 단계에서 다대다 관계 등 비효율적인 DB구조 개선을 위해 특정 규칙에 따라 모델을 수정하는 것

<span style="color:Tan">관계형 데이터베이스 설계 시 중복을 최소화하도록 데이터를 구조화하는 작업. 구조 안정성 최대화.</span>

<span style="color:IndianRed">관계형 데이터베이스라는 표현 기억.</span>

__이상(Anomaly)__  
십삼인의개발자가도로로질주하오  
제일의개발자가모르겠다고말하오

<span style="color:Tan">갱신 이상 : 속성 값을 갱신 할 때 일부 튜플의 정보만 갱신되어 정보에 모순이 생김
삽입 이상 : 데이터 삽입시 의도와 상관없는 값들이 함께 삽입되는 현상
삭제 이상 : 데이터 삭제시 의도와 상관없는 값도 삭제되는 현상</span>

<span style="color:IndianRed">SQLD에서도 안나온 것 같은데 이거.  
일단 기억해둘 것.</span>

__Oracle과 MySQL__  
오라클 – 상용 dbms. 보안 뛰어남. 대용량 데이터 처리에 능함. 비쌈.  
Mysql – 오픈소스. 점유율 높음.

<span style="color:Tan">Oracle은 대용량 처리에 적합함.
MySQL은 단일 DB로 제한되어 있어 매일 수백만번 액세스 해야하는 대용량 DB로는 부적합 함.  
SQL은 80 - 90%가 비슷하지만 서로 없는 명령어 nvl, varchar2 등이 존재함.</span>

<span style="color:IndianRed">문제없음</span>

## Spring

__프레임워크란__  
각종 클래스와 메소드 등 와꾸를 싹 짜 놓은걸 프레임워크라 부름.
표준이 정해져 있기 때문에 여럿이서 협업할 때 좋고 같은 프레임워크를 사용하는 다른 프로젝트에 투입되어도 바로 적응할 수 있음.

<span style="color:Tan">특정한 틀을 만들어 놓고 거기에 살을 붙여 놓음으로써 프로그램을 만드는 것입니다. 소프트웨어를 만들 때 뼈대가 되는 클래스, 인터페이스, 메서드 등을 미리 구현합니다.    
장단점 : 미리 구현해둔 코드를 사용하기 때문에 빨리 개발 할 수 있지만 익숙해지는데 시간이 걸릴 수 있고 의존성이 커지면 언어를 배우는 것이 아니라 프레임워크를 배우게 됩니다.   
↔ 라이브러리 : 틀과 구조를 결정한다는 측면에서 프레임워크와 활용도가 유사하지만 특정 기능이 필요한 경우 호출해서 사용하는 것. 프레임워크는 꼭 써야하는 틀이 있는 반면에 라이브러리는 필요한 기능을 호출해서 능동적으로 사용하는 것.</span>

<span style="color:IndianRed">문제없음</span>

__스프링 프레임워크란__  
Java 기반 동적 웹 개발 프레임워크. bean객체를 통한 의존성 주입이 가장 큰 특징. 또한 maven으로 라이브러리를 관리함.

<span style="color:Tan">자바 플랫폼을 위한 오픈 소스 애플리케이션 프레임워크. 하드웨어적인 구성이 필요 없는 경량 프레임워크. 자바 개발을 위한 프레임워크로 종속 객체를 생성해주고 조립해주는 기구로 개발자는 자신의 코드에 필요한 객체는 스프링을 통해서 주입받는 구조로 작성된다.</span>

<span style="color:IndianRed">자바 플랫폼을 위한 오픈 소스 애플리케이션 프레임워크. 표현 깔끔하니 기억해둘 것.</span>


__전자정부 프레임워크란__  
정부에서 권장하는 공공기관 웹페이지 개발 프레임워크를 말한다.  
적용대상 – Spring, myBatis, jsp, tiles 

<span style="color:Tan">대한민국 공공기관의 웹 서비스 개발 시 사용을 권장하는 프레임 워크로 spring, mybatis, jsp, 타일즈의 조합을 이야기 함.   
타일즈란? 웹페이지 상단이나 하단에 반복적으로 사용되는 정보를 한 곳으로 모아서 관리하는 프레임워크.</span>

<span style="color:IndianRed">문제없음</span>

__Dispatcher servlet__  
Spring FW에서 모든 request는 dispatcher servlet을 통해 controller로 전달됨

<span style="color:Tan">어플리케이션으로 들어오는 모든 request를 받는 관문. request를 실제로 처리할 controller에게 전달하고 그 결과값을 받아서 view에게 전달하여 적절한 응답을 생성 할 수 있도록 흐름을 제어 함.</span>

<span style="color:IndianRed">문제없음</span>

__의존성 주입__  
spring에서는 유지보수를 편하게 하기 위해 어떠한 객체가 필요할 때 그 객체의 class를 직접 만들지 않는다. 대신 먼저 bean 객체를 만든 뒤 bean 객체에 실제 class를 주입하는 방식을 사용하는데 이를 의존성 주입이라 한다.

<span style="color:Tan">특정 객체에 필요한 객체를 외부에서 결정해서 연결하는 것을 의미함.  
스프링에서 원하는 핵심적인 개념 중 하나라고 생각합니다. 설정 파일을 통해서 객체간의 의존관계를 설정하는 것. 직접 객체를 생성하지 않고 스프링에서 객체를 생성한 뒤에 사용할 객체에 주입시켜서 사용하게 하는 것.</span>

<span style="color:IndianRed">문제없음</span>

__MVC__  
Model, view, controller 로 이루어진 웹 디자인 패턴의 일종.
데이터 조작이 이루어지는 model, 사용자에게 보여지는 view, 로직의 흐름을 제어하는 controller가 분리된 형태이다.

<span style="color:Tan">Model, View, Controller의 합성어로 소프트 웨어 디자인 패턴.  
Model : 데이터  
View : jsp 파일들과 같이 실제로 보여지는 페이지.  
Controller : 사용자들의 요청을 받고 응답을 주는 로직 담당. 사용자가 접근한 url에 따라서 요청사항을 파악하고 요청에 맞는 데이터를 model에 의뢰하고 데이터를 view에 반영해서 사용자에게 보여줌.  
장점 : 코드 재사용</span>

<span style="color:IndianRed">장점 기억해둘 것.</span>


__Model1, Model2__  
Model1 방식은 하나의 jsp파일이 view와 controller 역할을 모두 수행하는 형태
Model2 방식은 view와 controller의 구분이 이루어짐. 개발자와 디자이너의 분업이 가능.

<span style="color:Tan">Model 1 : Controller 영역과 view 영역을 같이 구현하는 방식. 사용자의 요청을 jsp에서 표현하고 정리하고 처리하게 됨. 빠르게 쉽게 개발이 가능하지만 jsp 파일 자체가 너무 비대해지고 향후 유지보수에 어려움을 겪을 수 있음.  
Model 2 : Controller 영역과 view 영역을 분리해서 구현한 하는 방식. 웹 브라우저의 요청을 하나의 서블릿이 받게 됨. 서블릿은 웹 브라우저의 요청을 알맞게 처리한 뒤 그 결과를 jsp로 포워딩함. 디자이너와 개발자의 분업이 가능해서 유지보수에 유리하지만 설계에서 어려움을 겪을 수 있음.</span>

<span style="color:IndianRed">문제없음</span>

__쿠키와 세션__  
http는 요청에 응답한 후 연결을 끊어버리고, 클라이언트의 데이터도 갖고 있지 않다. 이 한계를 극복하기 위해 쿠키와 세션이 존재.
쿠키 사용자의 정보를 사용자의 브라우저에 저장하는 데이터. 보안에 취약하다.
세션 일정 시간동안 같은 사용자에게서 들어오는 요청을 하나의 상태로 보고 그 상태를 유지하는 기술. 브라우저를 닫거나 유효시간이 지날때까지 유지됨. 브라우저당 1개씩 생성. 

<span style="color:Tan">사용 이유? HTTP의 비연결성, 비상태성이라는 특징을 보완하기 위함 > 서버와 클라이언트가 통신을 할 때 통신이 연속적으로 이어지지 않고 끊어진다면 서버는 클라이언트가 누구인지 계속 인증해야함. 이는 번거롭고 웹 페이지 로딩을 느리게 하는 요인이되기도함. 이런 점을 해결하기 위한 방법이 쿠키와 세션.  
비연결성(Connectionless) : 클라이언트가 서버에 요청을 했을 때 그 요청에 맞는 응답을 보낸 후 연결을 끊는 처리 방식.  
비상태성(Stateless) : 클라이언트의 상태 정보를 가지지 않는 서버 처리 방식. 첫번째 통신에서 클라이언트와 데이터를 주고 받았다고 해도, 두번째 통신에서는 데이터 유지하지 않음.  
쿠키(Cookie) : 서버가 사용자의 웹 브라우저에 저장하는 데이터. Key와 Value로 구성되고 String 형태로 이루어져 있음. 브라우저마다 저장되는 쿠키는 다르고 서버에서는 브라우저가 다르면 다른 사용자로 인식함.  
ex) 방문했던 사이트에 다시 방문했을 때 아이디와 비밀번호 자동 입력, 오늘 이 창을 다시 보지 않기 체크
서버가 가지고 있는 것이 아닌 사용자에게 저장되기 때문에 임의로 고치거나 지울 수 있고 가로채기도 쉬어 보안 취약.  
세션 (Session) : 일정 시간동안 같은 사용자(브라우저)로부터 들어오는 일련의 요구사항을 하나의 상태로 보고 그 상태를 유지시키는 기술. 웹 브라우저 당 1개씩 생성되어 웹 컨테이너에 저장되며 브라우저 종료시 소멸됨. 저장 데이터에 제한이 없고 각 클라이언트에 고유 Session ID를 보유함.  
ex) 화면이 이동해도 로그인이 풀리지 않고 로그아웃하기 전까지 유지 됨</span>

<span style="color:IndianRed">예시를 기억해두자.</span>

__Servlet, Jsp__  
Servlet java파일에 html을 끼얹어
Jsp html에 java코드를 끼얹어

<span style="color:Tan">Servlet : Java에 html이 삽입  
jsp : html에 java가 삽입.</span>

<span style="color:IndianRed">문제없음</span>

__Maven__  
정해진 양식과 주소를 입력하면 인터넷에서 해당 라이브러리를 딱딱딱 알아서 다 해주는 프로젝트 관리 도구

<span style="color:Tan">프로젝트 관리 도구.  
settings.xml 또는 pom.xml 파일에 필요한 라이브러리만 적으면 maven 다운로드하고 설치 후 경로까지 지정해 줌.  
maven은 프로젝트 관리 도구로 프로젝트의 모든 단계에 사용하는 개발 도구이지만, 가장 많이 사용되는 용도는 프로젝트에 필요한 라이브러리를 자동으로 관리해주는 빌드 도구이다. 필요한 라이브러리 jar파일을 자동으로 다운 받을 수 있다.</span>

<span style="color:IndianRed">문제없음</span>

__AOP__  
Oop(객체지향프로그래밍)에서 한발짝 더 나아간 관점지향프로그래밍
자세한내용은 모르겟숴요

<span style="color:Tan">Aspect Oriented Programming, 관점 지향 프로그래밍. 객체 지향 프로그래밍에서 기능별로 class를 분리했음에도 로그, 트랜젝션 처럼 공통적으로 반복되는 중복 코드가 발생하는 단점을 해결하고자 나온 방식.  
공통의 관심 사항을 적용해서 발생하는 의존 관계의 복잡성과 코드 중복을 해소함.</span>

<span style="color:IndianRed"><https://engkimbs.tistory.com/746> 참고하자</span>

__Spring과 Springboot__  
Spring을 경량화시킨 서브프로젝트. 내장 서버가 존재한다는 특징이 있다.

<span style="color:Tan">스프링 부트는 스프링 프레임워크를 사용하는 프로젝트를 간편하게 셋업할 수 있는 서브 프로젝트임.</span>

<span style="color:IndianRed">문제없음</span>

__Mybatis__  
spring에서 사용하는 데이터베이스 연결 라이브러리.
기존 jdbc와 다르게 xml mapper 파일로 쿼리를 따로 관리한다.
자바 파일을 직접 수정할 필요가 없어짐. 간편한 유지보수.

<span style="color:Tan">기존 JDBC를 이용해서 프로그래밍을 하면 자바 소스 안에 sql문을 작성했지만 xml 파일에 sql문을 작성하므로 추수 수정 시에 다른 곳에는 아무런 영향이 없이 xml 파일만 수정하면 됨. 유지보수에 용이하고 가독성이 좋음.  
SQL문으로 DB에 접근하다보면 경우에 따라 SQL문 변경이 필요한 경우가 있음. mybatis를 활용해 단편적으로 제어문, 반복등의 처리가 가능하여 동적으로 변경이 가능하다.  
스프링과 마이바티스를 연계하는 라이브러리를 이용하면 직접 sql문을 호출하지 않고 자동화 처리가 가능하다</span>

<span style="color:IndianRed">문제없음</span>

__ORM__  
객체 중심의 query 컨트롤.
직접 쿼리를 작성하지 않고 해당 객체에 접근하여 메소드로 crud를 수행.
생산성 증가. 쿼리 작성에 소요되는 시간 대폭 절감.
Java 진영 orm으로는 jpa가 있음

<span style="color:Tan">객체와 관계형 데이터베이스의 데이터를 자동으로 연결해주는 개념. 객체 간의 관계를 바탕으로 SQL을 자동으로 생성해줌.</span>

<span style="color:IndianRed">문제없음</span>

__Request, response__  
요청 request 응답 response
스프링 기준 플로우
Request – dispatcherServlet – controller – (processComplete) – view return - response

<span style="color:Tan">request : 클라이언트에서 넘어오는 데이터를 받기 위한 객체  
response : 서버에서 클라이언트로 데이터를 전달하기 위한 객체</span>

<span style="color:IndianRed">문제없음</span>

__DAO__  
데이터 엑세스 오브젝트
db관련 로직 처리하는 클래스임

<span style="color:Tan">DAO(Data Access Object) 데이터베이스의 데이터에 접근을 위한 객체. 데이터베이스에 접근을 하기 위한 로직과 비즈니스 로직을 분리하기 위해서 사용</span>

<span style="color:IndianRed">데이터베이스에 접근하기 위한 로직과 비즈니스 로직을 분리하기 위해서 사용한다는 표현 기억해둘 것.</span>

__Annotation__  
@블라블라 형태로 사용
의존성 주입부터 각종 설정까지
스프링의 많은 기능들을 직관적이고 간편하게 처리할 수 있음

<span style="color:Tan">@Controller : 특정 클래스를 Controller로 등록하는 어노테이션.  
@RequestMapping : 컨트롤러로 등록된 클래스 내에 특정 메서드를 요청되는 URL과 매칭시키는 어노테이션.  
@Autowired : Spring에서 자동으로 의존성 주입을 하기 위한 어노테이션.  
@ResponseBody : 비동기 처리, JSON 형태 데이터 주고 받는 경우  
@RequestParam : 단일 파라미터를 전달 받을 때 사용함</span>

<span style="color:IndianRed">어노테이션 사용법은 아는데 정확한 정의에 대해 한 번 찾아보고 읽어보자.</span>

## 기타

__Array와 List__  
이거 자바기준? 자바로 설명함
배열은 생성할 때 길이를 반드시 정해야 함
리스트는 필요 없음 그때그때 달라짐

<span style="color:Tan">Array(배열)  
다수의 데이터를 묶어 효율적인 관리가 가능한 자료형. 데이터에 접근하기 위한 인덱스 존재하고 이를 통해서 데이터를 가져오기 때문에 조회 속도가 빠름. 데이터의 위치가 인덱스와 맵핑되어 고정되므로 추후 데이터가 삭제되는 경우 배열의 빈 부분의 메모리가 낭비 됨. 정의와 동시에 길이를 지정하며 길이를 바꿀 수 없는 정적 자료형. > 삽입, 삭제 시 리스트보다 느림.  
List  
순서가 있고 중복이 허용됨. ArrayList, LinkedList. 리스트는 자동으로 엘리먼트를 수용할 수 있는 크기가 조정되고, 리스트 내의 실제 개수를 알려줌. 검색 시 배열보다 느리고 추가, 삭제가 빠름.

<span style="color:IndianRed">문제없음</span>

__Stack과 Que__  
스택은 선입선출
큐는 마지막에 넣은걸 꺼냄

<span style="color:Tan">Stack : LIFO, 마지막에 들어온 것이 먼저 나가는 구조. 데이터 삽입 연산을 push, 삭제 연산을 pop이라고 함. 삽입과 삭제가 일어나는 위치는 top. 비어있는 스택에서 원소를 추출하려고 할 때 stack underflow라고 하며, 스택이 넘치ㅣ는 경우에는 stack overflow라고 함.  
ex) 웹 브라우저에서 뒤로가기, 실행 취소  
Queue : FIFO, 먼저 들어온 것이 먼저 나간다는 뜻.  
ex) 은행, 공연장. 한쪽 끝에서는 삽입, 한족 끝에서는 삭제 작업이 이루어짐. 삭제 연산이 수행되는 곳을 front, 삽입 연산이 수행되는 곳을 rear. ex) 우선 순위가 같은 작업 예약, 콜센터 객 대기 시간</span>

<span style="color:IndianRed">문제없음</span>

__http와 https__  
http에서 보안성 추가한게 https

<span style="color:Tan">http : 웹 서버 통신을 위한 프로토콜, 80번 포트 사용.  
https : 암호화된 통신을 제공하는 http이므로 느리지만 개인정보등의 보안 유지를 위해서 사용함.</span>

<span style="color:IndianRed">문제없음</span>

__url과 uri__  
url은 서버상의 파일 위치
uri는 인터넷 상의 자원을 식별하기 위한 문자 구성 (get방식 parameter같은거 다 들어감)

<span style="color:Tan">URL : www.google.com/search : 서버 상의 파일들의 위치  
URI : www.google.com/search?q=ui : 인터넷 상의 자원을 식별하기 위한 문자 구성</span>

<span style="color:IndianRed">문제없음</span>

__get방식과 post방식__  
get방식 parameter를 주소로 그냥 쏴버림(사용자 눈에도 보임)
post방식 객체도 보낼 수 있음(사용자 눈에는 안보이지만 개발자도구로 뜯으면 다 보임)

<span style="color:Tan">GET : 클라이언트에서 서버로 데이터를 전달할 때, 주소 뒤에 key와 value가 결합된 쿼리 스트링 형태로 전달하는 것. ?type=get. 길이에 제한이 있으므로 전송 데이터의 한계가 있고 post 방식보다 상대적으로 전송 속도가 빠름  
POST : 일정 크기 이상의 데이터를 보낼 때 사용. 쿼리 스트링 데이터 뿐만이 아니라 라디오 버튼, 텍스트 박스 같은 객체들의 값고 전송 가능.  
둘 다 보안상으로 취약하다. post의 경우 눈에 보이지 않아서 안전해 보일 수 있지만 크롬 개발자 도구를 이용하면 내용을 확인 할 수 있다.</span>

<span style="color:IndianRed">문제없음</span>

