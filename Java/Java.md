# Java

###### : Sun Microsystems. Inc. 에서 개발하여 1996년 1월에 공식적으로 발표한 객체지향 프로그래밍 언어이다. 2010년에 oracle사에 인수되면서 Java는 oracle사의 제품이 되었다.

---

1. 운영체제에 독립적이다.
2. 객체지향언어이다.
3. 비교적 배우기 쉽다.
4. 자동 메모리 관리(Garbage Collection)
5. 네트워크와 분산처리를 지원한다.
6. 멀티쓰레드(multi-thread)를 지원한다.
7. 동적 로딩(Dynamic Loading)을 지원한다.

## 자바 가상 머신(JVM : Java virtual machine)

## 자바 개발도구(JDK : Java Development Kit) 설치

## 자바 개발도구(JDK : Java Development Kit) 설정

## 자바 API문서 설치

## 자바 프로그램 작성하기

> * 편집기 : 이클립스(eclipse)

```java
public class Test {
	public static void main(String[] args) {
		System.out.println("Hello, world");
	}
}
```

###### (<u>Java는 대소문자를 구분합니다.</u>)

자바에서 모든 코드는 반드시 클래스 안에 존재해야 하며, 서로 관련된 코드들을 그룹으로 나누어 별도의 클래스를 구성하게 된다. 그리고 이 클래스들이 모여 하나의 Java 애플리케이션을 이룬다.
(package문과 import문은 예외적으로 클래스의 밖에 작성한다.)

> - 클래스 작성법
>
>   ```java
>   class 클래스이름{
>   	/* 주석 */
>   }
>   ```

`public static void main(String[] args)`를 main메서드의 선언부라고 하며, main메서드의 선언부 다음에 나오는 괄호`{} `는 메서드의 시작과 끝을 의미합니다. Java 애플리케이션은 main메서드의 호출로 시작해서 main메서드의 첫 문장부터 마지막 문장까지 수행을 마치면 종료된다. main메서드는 Java애플리케이션의 시작점이므로 main메서드 없이는 Java 애플리케이션을 실행할 수 없기 때문에  Java애플리케이션을 실행할 때는 'java.exe' 다음에 main메서드를 포함한 클래스의 이름을 적어줘야한다.

> cmd.exe에서 다음과 같이 Java 애플리케이션을 실행시켰을 때, `c:\jdk1.8\work>java Hello`
>
> 	1. 프로그램의 실행에 필요한 클래스(*.class파일)를 로드한다.
>  	2. 클래스파일을 검사한다.(파일형식, 악성코드 체크)
>  	3. 지정된 클래스(Hello)에서 `main(String[] args)`를 호출한다.

##### 이클립스로 자바 프로그램 개발하기

1. 새로운 프로젝트를 생성하기 위해 메뉴에서 File > New > Java Project를 클릭한다.
2. Project name으로 'Hello'를 입력하고 'Finish'버튼을 누른다.
3. 패키지 익스플로서(Package Explorer) 아래에 Hello 프로젝트가 생성된 것을 확인하자. 이제 Hello클래스를 새로 추가하기 위해 Hello프로젝트 위에서 우클릭하여, 메뉴 New 아래의 Class를 클릭한다.
4. 클래스의 이름으로 Hello로 입력하고, 아래의 체크박스를 체크한 후에 'Finish'버튼을 클릭한다.
5. Hello프로젝트에  Hello.java라는 파일이 생성되고, 우측에는 이 파일의 내용이 자동으로 작성되어 나타난다. main메서드에 `System.out.println("Hello, world");`를 추가하고 실행버튼을 누른다.
6. console창에 `Hello, world`가 출력된다.

##### 이클립스 

이클립스의 화면은 여러개의 작은 창들로 이루어져 있는데, 이 하나의 창을 뷰(view)라 부르고 이 뷰들로 구성된 화면 전체를 퍼스펙티브(perspective)라고 한다.

> 퍼스펙티브 저장 : '메뉴 Window > Perspective > Save Perspective As...'.
> 퍼스펙티브 불러오기 :  '메뉴 Window > Perspective > Open Perspective As...'.
> 퍼스펙티브 되돌리기 :  '메뉴 Window > Perspective > Reset Perspective As...'.

이클립스에서 작성한 파일이 저장되는 공간을 워크스페이스(workspace)라고 하며, 이클립스를 처음 실행할 때 워크스페이스로 사용할 폴더를 지정하는 화면이 나타난다.

>새로운 워크스페이스 만들기 : '메뉴 File > Switch Workspace > Other..'

* 이클립스 단축키

  | 명령 | 단축키 |
  | :--: | :----: |
  |      |        |

  > 단축키의 설정 및 변경
  >
  >  '메뉴 Window > Preferences' > 'General > Keys' > 단축키 변경 > 'Binding'

이클립스 자동완성 기능(Content Assist)는 특정 단어나 문자를 입력한 후에 자동완성 기능 단축키 `Ctrl+space`를 누르면, 코드가 자동으로 완성되는 편리한 기능이다. 또한 특정 단어를 입력하고 자동완성 단축키를 누르면, 지정된 형식으로 자동완성되게 할 수도 있다. 이 단어를 '템플릿(Template)'이라고 한다.

> 템플릿 추가, 삭제 또는 변경
> '메뉴 Window > Preferences' > 'Java > Editor > Templates'

## 주석(comment)

작성하는 프로그램의 크기가 커질수록 프로그램을 이해하고 변경하는 일이 점점 어려워진다. 주석을 이용해서 프로그램 코드에 대한 설명을 적절히 덧붙여 놓으면 프로그램을 이해하는 데 많은 도움이 된다.

> * 범위 주석
>
>   ```java
>   /* 사이의 내용을 주석으로 간주한다. */
>   ```
>
> * 한 줄 주석
>
>   ```java
>   // 부터 라인 끝까지의 내용은 주석으로 간주된다.
>   ```

주석이 많다고 해서 프로그램의 성능이 떨어지는 일은 없다.

## 자주 발생하는 에러와 해결방법

1. cannot find symbol 또는 cannot resolve symbol

   지정된 변수나 메서드를 찾을 수 없다는 뜻으로 선언되지 않은 변수나 메서드를 사용하거나, 변수 또는 메서드의 이름을 잘못 사용한 경우에 발생한다. 자바에서는 대소문자 구분을 하기 때문에 철자 뿐 만아니라 대소문자의 일치여부도 꼼꼼하게 확인해야한다.

2. `';'` expected

   세미콜론`';'`이 필요한 곳에 없다는 뜻이다. 자바의 모든 문장의 끝에는 `';'`을 붙요주어야 하는데 가끔 이를 잊고 실수하기 쉽다.

3. Exception in thread "main" java.lang.NoSuchMethodError: main

   'main메서드를 찾을 수 없다.'는 뜻인데 실제로 클래스 내에 main메서드가 존재하지 않거나 메서드의 선언부에 오타가 존재하는 경우에 발생한다. 이 에러의 해결방법은 main 메서드가 클래스에 정의되어 있는지 확인라고, 정의되어 있다면 main메서드의 선언부에 오타가 어뵤는지 확인한다. 자바는 대소문자를 구별하므로 대소문자의 일치여부까지 정확히 확인해야한다.

4. Exception in thread "main" java.lang.NoClassDefFoundErroe: Hello

   'Hello라는 클래스를 찾을 수 없다.'는 뜻이다. 클래스 'Hello'의 철자, 특히 대소문자를 확인해보고 이상이 없으면 클래스파일(*.class)이 생성되었는지 확인한다.

5. illegal start of expression

   문장에 문법적 오류가 있다는 뜻이다. 괄호`'()'`나 `'{}'`를 열고서 닫지 않거나, 수식이나 if문, for문 등에 문법적 오류가 있을 때 또는 public이나 static과 같은 키워드를 잘못 사용한 경우에도 발생한다.

6. class, interface, or enum expected

   '키워드 class나 interface 또는 enum이 없다.'이지만 보통 괄호 `'()'` 또는 `'{}'`의 개수가 일치하지 않는 경우에 발생한다. 열린괄호`'{'`와 닫힌괄호`'}'`의 개수가 같은지 확인하자.