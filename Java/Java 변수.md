# Java 변수

---

## print()과 println()

화면에 글자를 출력할 때는 `System.out.println();`을 사용한다. 괄호() 안에 출력하고자 하는 내용을 넣으면 된다.

```java
System.out.println("Hello, world");		 // 화면에 Hello, world 출력
System.out.println(3+5); 				// 화면에 8을 출력
System.out.println("3+5"); 				// 화면에 3+5를 출력
```

print()는 줄바꿈을 하지 않고, println() 줄바꿈을 한다.

```java
System.out.println("Hello, world");		 // 괄호 안의 내용을 출력하고 줄바꿈을 한다.
System.out.print("Hello, world");		 // 괄호 안의 내용을 출력하고 줄바꿈을 하지 않는다.
```

## 사칙연산이 포함된 식

```java
System.out.println(5+3); 				// 화면에 5+3의 결과인 8을 출력한다.
System.out.println(5-3); 				// 화면에 5-3의 결과인 2을 출력한다.
System.out.println(5*3); 				// 화면에 5*3의 결과인 15을 출력한다.
System.out.println(5/3); 				// 화면에 5/3의 결과인 1을 출력한다.
```

## 변수의 선언과 저장

프로그래밍을 하다 보면 값을 저장해 둘 공간이 필요헌데, 그 공간을 변수(variable)라 한다.

> 변수타입 변수이름 = 리터럴;
> `=` : 대입 연산자(assignment operator)로 오른쪽의 값을 왼쪽에 저장하라는 의미 이다.

* 자주 쓰이는 변수의 타입

  <table>
      <tr>
          <th align="center">분류</th>
          <th>변수의 타입</th>
          <th>설명</th>
      </tr>
      <tr>
          <td align="justify" rowspan="2">숫자</td>
          <td>int<br/>long</td>
          <td>정수(integer)를 저장하기 위한 타입(20억이 넘을 땐 long)</td>
      </tr>
      <tr>
          <td>flaot<br/>double</td>
          <td>실수(floating-point number)를 저장하기 위한 타입 (float는 오차없이 7자리, double은 15자리)</td>
      </tr>
      <tr>
          <td align="center" rowspan="2">문자</td>
          <td>char</td>
          <td>문자(character)를 저장하기 위한 타입</td>
      </tr> 
      <tr>
          <td>String</td>
          <td>여러 문자(문자열, string)를 저장하기 위한 타입</td>
      </tr>
  </table>

* 상수(constant)

  '상수(constant)'는 변수와 마찬가지로 '값을 저장할 수 있는 공간'이지만, 변수와 달리 한법 값을 저장하면 다른 값으로 변경할 수 없다. 상수를 선언하는 방법은 변수의 타입 앞에 키워드 'Final'을 붙여주기만 하면 된다.

  > Final 변수타입 변수이름 = 리터럴;

  일단 상수에 값이 저장된 후에는 상수의 값을 변경하는 것이 허용되지 않는다. 상수의 이름은 모두 대문자로 하는 것이 관례이며, 여러 단어로 이루어져있는 경우 `_` 로 구문한다.

* 리터럴(literal)

  변수(variable) : 하나의 값을 저장하기 위한 공간
  상수(constant) : 값을 한번만 저장할 수 있는 공간
  리터럴(literal) : 그 자체로 값을 의미하는 것

  |  종류  |            리터럴            | 접미사 |
  | :----: | :--------------------------: | :----: |
  | 논리형 |         false, true          |  없음  |
  | 정수형 | 123, 0b0101, 077, 0xFF, 100L |   L    |
  | 실수형 | 3.14, 3.0e8, 1.4f, 0x1.op-1  |  f, d  |
  | 문자형 |        'A', '1', '\n'        |  없음  |
  | 문자열 |  "ABC", "123", "A", "true"   |  없음  |

* 문자열 결합

  > 문자열 + any type --> 문자열 + 문자열 --> 문자열
  > any type + 문자열 --> 문자열 + 문자열 --> 문자열

  덧셈 연산자(+)는 피연산자가 모두 숫자일 때는 두 수를 더하지만, 피연산자 중 어느 한 쪽이 String이면 나머지 한 쪽을 먼저 String으로 변환한 다음 두 String을 결합한다.

## 기본형과 참조형

자료형은 크게 '기본형'과 '참조형' 두 가지로 나눌 수 있는데, 기본형 변수는 실제 값(data)을 저장하는 반면, 참조형 변수는 어떤 값이 저장되어 있는 주소(memory address)를 값으로 갖는다. Java는 참조형 변수 간의 연산을 할 수 없다.

> **기본형(primitive type)**
> 논리형(boolean), 문자형(char), 정수형(byte, short, int, long), 실수형(float, double) 계산을 위한 실제 값을 저장한다. 모두 8개
>
> **참조형(reference type)**
> 객체의 주소를 저장한다. 8개의 기본형을 제외한 나머지 타입.

* 기본형

  | 종류 \ 크기 | 1 byte  | 2 byte | 4 byte | 8 byte |
  | :---------: | :-----: | :----: | :----: | :----: |
  |   논리형    | boolean |        |        |        |
  |   문자형    |         |  char  |        |        |
  |   정수형    |  byte   | short  |  int   |  long  |
  |   실수형    |         |        | float  | double |

  > * boolean은 true와 false 두 가지 값만 표현할 수 있으면 되므로 가장 작은 크기인 1 byte.
  > * char은 Java에서 유니코드를 사용하므로 2 byte.
  > * byte는 크기가 1 byte라서 byte.
  > * int(4 byte)를 시준으로 짧아서 short(2 byte), 길어서 long(8 byte). (short <--> long)
  > * float는 실수값을 부동소수점(floating-point)방식으로 저장하기 때문에 float.
  > * double은 float보다 두 배의 크기 (8 byte)를 갖기 때문에 double.

  <table>
      <tr align="center">
      	<th rowspan="2">자료형</th>
          <th rowspan="2">저장 가능한 값의 범위</th>
          <th colspan="2">크기</th>
      </tr>
      <tr align="center">
      	<th>bit</th>
          <th>byte</th>
      </tr>
      <tr align="center">
      	<td>boolean</td>
          <td>false, true</td>
          <td>8</td>
          <td>1</td>
      </tr>
      <tr align="center">
      	<td>char</td>
          <td>'\u0000' ~ '\uffff' (0~2^16-1, 0~65535)</td>
          <td>16</td>
          <td>2</td>
      </tr>
          <tr align="center">
      	<td>byte</td>
          <td>-128 ~ 127 (-2^7~2^-1)</td>
          <td>8</td>
          <td>1</td>
      </tr>
      <tr align="center">
      	<td>short</td>
          <td>-32,768 ~ 32767 (-2^15~2^15-1)</td>
          <td>16</td>
          <td>2</td>
      </tr>
      <tr align="center">
      	<td>int</td>
          <td>-2,147,483,648 ~ 2,147,483,647 (-2^31~2^31-1, 약 ±20억)</td>
          <td>32</td>
          <td>4</td>
      </tr>
      <tr align="center">
      	<td>long</td>
          <td>-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807(-2^63~2^63-1)</td>
          <td>64</td>
          <td>8</td>
      </tr>
      <tr align="center">
      	<td>float</td>
          <td>1.4E-45 ~ 3.4E38 (1.4*10^-45~3.4*10^38)</td>
          <td>32</td>
          <td>4</td>
      </tr>
      <tr align="center">
      	<td>double</td>
          <td>4.9ㄸ-324 ~ 1.8E308(4.9*10^-324~1.8*10^308)</td>
          <td>64</td>
          <td>8</td>
      </tr>
  </table>

## 화면으로부터 입력받기

* Scannar 클래스

  ```java
  import java.util.Scanner; 						// Scanner클래스를 사용하기 위해 추가
  public class Test {
  	public static void main(String[] args) {
  		Scanner sc = new Scanner(System.in); 	 // Scanner 클래스의 객체를 생성
  		String input = sc.nextLine();			// 입력받은 내용을 input에 저장
  		int num = Integer.parseInt(input); 		 // 입력받은 내용을 int타입의 값으로 변환
  	}
  }
  ```

## 오버플로우

- 정수형의 오버플로우

  타입이 표현할 수 있는 값의 범위를 넘어서는 것을 오버플로우(overflow)라고 한다. 오버플로우가 발생했다고 해서 에러가 발생하는 것은 아니다. 다만 예상했던 결과는 얻지 못핟다. 오버플로우가 발생하지 않게 충분한 크기의 타입을 선택해서 사용해야한다.

  > 최대값 + 1 --> 최소값
  > 최소값 - 1 --> 최댓값

- 부호있는 정수의 오버플로우

  부호없는 정수와 부호있는 정수는 표현범위 즉, 최댓값과 최솟값이 다르기 때문에 오버플로우가 발생하는 시점이 다르다. 부호없는 정수는 2진수로 '0000'이 될 때 오버플로우가 발생하고, 부호있는 정수는 부호비트가 0에서 1이 될 때 오버플로우가 발생한다.

  > 최소값 - 1 --> 최댓값
  > 최대값 + 1 --> 최소값

## 타입 간의 변환방법

1. 숫자를 문자로 변환 - 숫자에 '0'을 더한다.

   `(char)(3 + '0')` ---> `3`

2. 문자를 숫자로 변환 - 문자에서 '0'을 뺀다.

   `'3' - '0'` ---> `3`

3. 숫자를 문자열로 변환 - 숫자에 빈 문자열("")을 더한다.

   `3 + ""` ---> `"3"`

4. 문자열을 숫자로 변환 - `Integer.parseInt()` 또는 `Double.parseDouble()`을 사용한다.

    `Integer.parseInt("3")` ---> `3`
    `Double.parseDouble("3.14")` ---> `3.14`

5. 문자열을 무낮로 변환 - charAt(0)을 사용한다.
   `"3".charAt(0)` ---> `'3'`

6. 문자를 문자열로 변환 - 빈 문자열("")을 더한다.

   `'3' - ""` ---> `"3"`

