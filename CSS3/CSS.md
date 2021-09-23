# CSS

######  : Cascading Style Sheets

---

CSS의 역할은 HTML로는 부족한 레이아웃이나 폰트 등에 다양성을 부여합니다. 폰트 크기, 자간 설정, 행간의 높이, 페이지 여뱍을 마음대로 조절할 수 있습니다. 웹페이지의 레이아웃을 자유롭게 설계하여 배치할 수 있습니다. 링크할 때 밑줄의 변형도 가능해서 가족성을 높일 수 있습니다.

- 스타일 시트 선언

```css
<style type="text/css">
	코드작성
</style>
```

(`type="text/css"`는 생략이 가능합니다.)

## CSS 코드 만드는 방법

1. **내부 스타일 시트**는 HTML 문서 한의 `<style>`과 `</style>` 안에  CSS 코드를 추가하는 방법입니다.

   ```html
   <html>
   	<head>
   		<meta charset="UTF-8">
   		<title>Insert title here</title>
   		<style type="text/css">
   			('CSS 코드')
   		</style>
   	</head>
   	<body>
   		<h1>Hello World</h1>
   	</body>
   </html>
   ```

2. **외부 스타일 시트**는 별도의  CSS 파일을 만들어 놓고 HTML 문서와 연결하는 방법입니다.

   * link를 이용

     ```html
     <html>
     	<head>
     		<meta charset="UTF-8">
     		<title>Insert title here</title>
     		<link rel="stylesheet" type="text/css" href="style.css">
     	</head>
     	<body>
     		<h1>Hello World</h1>
     	</body>
     </html>
     ```

     CSS 파일을 적용시킬 HTML 문서에 `<link>`로 연결하여 사용하면 됩니다.

   * @import 이용

     ```html
     <html>
     	<head>
     		<meta charset="UTF-8">
     		<title>Insert title here</title>
     		<style>
     			@import url("style.css");
     		</style>
     	</head>
     	<body>
     		<h1>Hello World</h1>
     	</body>
     </html>
     ```

     `@import url(" ")`은 여러 개의 CSS 파일을 한 번에 가져올 수 있습니다.

     > `<link>` 태그와 `@import`는 비슷하게 사용하지만 성능(속도) 면에서는 `<link>`가 더 빠릅니다.

3. HTML 태그의 style 속성에 CSS 코드를 추가하는 방법입니다. (**인라인 스타일 시트**)

   ```html
   <html>
   	<head>
   		<meta charset="UTF-8">
   		<title>Insert title here</title>
   	</head>
   	<body>
   		<h1 style="color: red;">Hello World</h1>
   	</body>
   </html>
   ```

> * CSS 색상 표현
>
>   | 색상 단위 |          설명           |         사용 예         |
>   | :-------: | :---------------------: | :---------------------: |
>   | 색상 이름 |      색상 상수 값       |  black, white, yellow   |
>   |    RGB    | red, green, blue의 조합 | rgb(255.0.0),rgb(0.0.0) |
>   |    HEX    |  색상을 16진수로 표현   |   #fff, #000, #ffcc00   |

## CSS 선택자

* 전체 선택자 (`*`)

  > *{속성: 값;}

  ```html
  <html>
  	<head>
  		<meta charset="UTF-8">
  		<title>Insert title here</title>
  		<style>
  			*{ 
                  font-family:"Comic Sans MS"; 
  			}
  		</style>
  	</head>
  	<body>
  		<h1>Hello World</h1>
  	</body>
  </html>
  ```

* 타입(태그) 선택자 (`p`,`div`,`span` 등)

  > 태그명{속성: 값;}

  ```html
  <html>
  	<head>
  		<meta charset="UTF-8">
  		<title>Insert title here</title>
  		<style>
  			h1{ 
                  font-family:"Comic Sans MS"; 
  			}
  		</style>
  	</head>
  	<body>
  		<h1>Hello World</h1>
  	</body>
  </html>
  ```

* 아이디(ID) 선택자 (`#ID`)

  >#ID명{속성: 값;}

  ```html
  <html>
  	<head>
  		<meta charset="UTF-8">
  		<title>Insert title here</title>
  		<style>
  			#myid{ 
                  font-family:"Comic Sans MS"; 
  			}
  		</style>
  	</head>
  	<body>
  		<h1 id="myid">Hello World</h1>
  	</body>
  </html>
  ```

* 클래스(Class) 선택자 (`.class`)

  >.클래스명{속성: 값;}
  >
  >태그명.클래스명{속성: 값;}

  ```html
  <html>
  	<head>
  		<meta charset="UTF-8">
  		<title>Insert title here</title>
  		<style>
  			.myclass{ 
  				font-family:"Comic Sans MS";
  			}
  			h2.myclass{ 
  				font-family:"HY견고딕";
  			}
  		</style>
  	</head>
  	<body>
  		<h1 class="myclass">Hello World</h1>
  		<h2 class="myclass">Hello World</h2>
  	</body>
  </html>
  ```

  > ID는 '유일'한 요소에 스타일을 적용합니다. 한 문서에서 ID는 한 번만 사용 가능합니다. 상단 메뉴바, 하단 정보, 홈페이지 로고처럼 유일한 것들을 선택할 때 사용합니다.
  >
  > CLASS는 '복수' 요소에 스타일을 적용합니다. 한 문서에서 여러 번 사용 가능합니다. 소제목처럼 반복되는 요소에 사용합니다.

* 속성 선택자

  > 태그명[속성명]{속성: 값;}

  ```
  
  ```

* 가상 클래스 선택자

  > 태그명:가상요소명{속성: 값;}

  ```
  
  ```

* 후손(하위) 선택자

  > 선택자 선택자{속성: 값;}

  ```
  
  ```

* 자식 선택자

  > 선택자 > 선택자{속성: 값;}

  ```
  
  ```

* 형제 선택자

  > 선택자 ~ 선택자{속성: 값;}

  ```
  
  ```

* 인접 형제 선택자

  > 선택자 + 선택자{속성: 값;}

  ```
  
  ```

* 그룹 선택자

  ```
  <html>
  	<head>
  		<meta charset="UTF-8">
  		<title>Insert title here</title>
  		<style>
  			h1, h2{ 
  				font-family:"Comic Sans MS";
  			}
  		</style>
  	</head>
  	<body>
  		<h1 class="myclass">Hello World</h1>
  		<h2 class="myclass">Hello World</h2>
  	</body>
  </html>
  ```

> * 선택자의 우선순위
>   인라인 선택자 > 아이디 선택자 > 클래스 선택자 > 태그 선택자

##  CSS 주요 스타일 속성

* 문자 스타일 속성'

  |     속성      |                             설명                             |
  | :-----------: | :----------------------------------------------------------: |
  | font-family:  |                      글꼴을 지정합니다.                      |
  |  font-size:   |                  문자의 크기를 설정합니다.                   |
  |  font-style:  | 문자의 기울기를 설정합니다.<br />(normal, italic, oblique, initial, inherit) |
  | font-weight:  | 문자의 굵기를 설정합니다.<br />(normal, bold, bolder, lighter, italic, inherit) |
  | font-variant: | 작은 대문자를 표시합니다.<br />(normal, small-caps, initial, inherit) |
  | line-height:  |                    줄 간격을 조절합니다.                     |
  |     font:     |           font  속성을 한 번에 기술할 수 있습니다.           |

* 문단 스타일 속성

  |       속성       |                             설명                             |
  | :--------------: | :----------------------------------------------------------: |
  | text-decoration: | 문자에 밑줄 또는 취소선 등을 넣습니다.<br />(none, underline, overline, line-through, inherit) |
  |   text-align:    | 문단을 왼쪽, 가운데, 오른쪽 정렬합니다.<br />(left, right, center, justify) |
  |   text-indent:   |         문단의 들여쓰기 또는 내어 쓰기를 지정합니다.         |
  | text-transform:  | 영문자 모두를 대문자로 또는 소문자로 변경합니다.<br />(none, capitalize, uppercase, lowercase, inherit) |
  | letter-spacing:  |                  글자의 간격을 조절합니다.                   |
  |  word-spacing:   |                 단어 간의 간격을 조절합니다.                 |
  | vertical-align:  | 문자와 문자간의 수직 정렬을 조절합니다.<br />(baseline, top, middle, bottom 등) |
  |   white-space:   | 줄바꿈에 대한 설정을 합니다.<br />(normal, nowrap, pre, pre-line, pre-wrap, inherit) |

* 테두리 스타일 속성

  |     속성      |                             설명                             |
  | :-----------: | :----------------------------------------------------------: |
  | border-width: | 선의 굵기를 지정합니다. px이나 em등의 단위를 사용하며 주로 px를 많이 사용합니다. |
  | border-style: | 선의 형태를 지정합니다.<br />(none, solid, dotted, dashed, double, groove 등) |
  | border-color: | 선의 색상을 지정합니다. 색상 이름이나 색상 코드가 들어갈 수 있습니다. |

* 리스트 스타일 속성

  |         속성         |                             설명                             |
  | :------------------: | :----------------------------------------------------------: |
  |   list-style-type:   | 리스트 앞에 오는 불릿의 타입을 결정하는 속성입니다.<br />(none, disc, circle, square, decimal, lower-alpha, upper-alpha, lower-roman, upper-roman) |
  |  list-style-image:   |     리스트 불릿을 이미지로 사용하고자 할 때 사용합니다.      |
  | list-style-position: | 리스트의 불릿이 밖에 있을지 안에 있을지를 결정합니다.<br />(outside, inside, inherit) |
  |     list-style:      |          리스트 속성들을 한번에 사용할 수 있습니다.          |

* 배경 스타일 속성

  |          속성          |                             설명                             |
  | :--------------------: | :----------------------------------------------------------: |
  |   background-color:    |                배경에 색상을 넣는 속성입니다.                |
  |   background-image:    |     배경에 이미지를 넣는 속성입니다.<br />(url("경로"))      |
  |   background-repeat:   | 배경 이미지의 반복 여부를 설정하는 속성입니다.<br />(repeat, repeat-x,  repeat-y, no-repeat, inherit) |
  |  background-position:  | 이미지의 위치를 설정하는 속성입니다.<br />(px, %, left, right, top, bottom, center, inherit) |
  | background-attachment: | 화면을 스크롤 할 때 배경 이미지가 어떻게 동작하는지를 설정하는 속성입니다.<br />(scroll, fixed, inherit) |

* 테이블 스타일 속성

  |       속성       |                             설명                             |
  | :--------------: | :----------------------------------------------------------: |
  | border-collapse: | 테이블 셀 간의 간격 여부를 설정합니다.<br />(separate, collapse, inherit) |
  | border-spacing:  | 테이블 셀 간의 공백 크기를 조절해 주는 속성입니다. border-collapse: separate인 상태에서만 가능합니다. |
  |   empty-cells:   | 테이블에서 빈 셀에 대해 그 셀의 테두리나 배경을 브라우저에 보여줄지 보여주지 않을지를 설정합니다. border-collapse: separate인 상태에서만 가능합니다.<br />(hide, show, inherit) |
  |  table-layout:   | 셀의 너비를 고정 또는 가변으로 할지를 설정합니다.<br />(auto, fixed, inherit) |
  | vertical-align:  |    셀 안에서 수직 정렬합니다.<br />(top, middle, bottom)     |
  |  caption-side:   | 캡션의 위치를 정하는 속성(property)입니다.<br />(top, bottom, initial, inherit) |

* 박스 모델 속성

  * 여백의 속성

    |     속성      |                          설명                           |
    | :-----------: | :-----------------------------------------------------: |
    |    margin     | 여백 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다. |
    |  margin-top   |               위쪽 여백 값을 설정합니다.                |
    | margin-right  |              오른쪽 여백 값을 설정합니다.               |
    | margin-bottom |              아래쪽 여백 값을 설정합니다.               |
    |  margin-left  |               왼쪽 여백 값을 설정합니다.                |

  * 패딩의 속성

    |      속성      |                             설명                             |
    | :------------: | :----------------------------------------------------------: |
    |    padding     | 모든 padding 속성을 이용한 스타일을 한 줄에 설정할 수 있습니다.<br />(top, right, bottom, left) |
    |  padding-top   |                  위쪽 패딩 값을 설정합니다.                  |
    | padding-right  |                 오른쪽 패딩 값을 설정합니다.                 |
    | padding-bottom |                 아래쪽 패딩 값을 설정합니다.                 |
    |  padding-left  |                  왼쪽 패딩 값을 설정합니다.                  |

  * 테두리의 속성

    |     속성      |                             설명                             |
    | :-----------: | :----------------------------------------------------------: |
    |    border     | 태그의 테두리를 설정하는 속성입니다. 세부적인 속성들을 한 번에 쓸 수 있습니다.<br />(border-width, border-style, border-color) |
    | border-style  |             테두리를 다양한 모양으로 설정합니다.             |
    | border-width  |                 테두리의 너비를 설정합니다.                  |
    | border-color  |                 테두리의 색상을 설정합니다.                  |
    |  border-top   |         테두리의 top 부분 속성을 한 번에 설정합니다.         |
    | border-right  |        테두리의 right 부분 속성을 한 번에 설정합니다.        |
    |  border-left  |        테두리의 left 부분 속성을 한 번에 설정합니다.         |
    | border-bottom |       테두리의 bottom 부분 속성을 한 번에 설정합니다.        |

## CSS 고급 스타일 효과

* Shadow와 Grandient

  > - Shadow
  >
  >   text-shadow: h-shadow v-shadow blur-radius spread-distance color;
  >   box-shadow: h-shadow v-shadow blur-radius spread-distance color;

  > * Grandient

* 