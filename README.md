# 코딩테스트 솔루션
## 자바 2021년 2학기 도제반 방과후
### 9/13(월) 도전문제 : 구구단
#### 1.구구단 출력 Level 1
```
"실행 화면 예시" 와 같이 2단부터 9단까지 구구단을 출력하는 코드를 완성하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		for(int i=2; i<=9; i++) {
			System.out.println("구구단 " + i + "단");
			// 이곳의 코드를 완성하세요
			for(int j=1; j<=9; j++) {
				System.out.println(i + " x " + j + " = " + i*j);
			}
		}
	}
}
```

#### 2.구구단 출력 Level 2
```
다음과 같이 구구단 함수를 호출했을 때
gugudan(7);

"실행 화면 예시"와 같이 결과가 나오도록 코드를 완성하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		// 구구단 함수 호출
		gugudan(7);
	}
	
	// 이곳의 코드를 완성하세요
	static void gugudan(int d) {
		for(int i=1; i<=9; i++) {
			System.out.println(d + " x " + i + " = " + d*i);
		}
	}
}
```

#### 3.구구단 출력 Level 3
```
다음과 같이 구구단 객체를 생성한 후 show 함수를 호출했을 때
Gugudan gugudan = new Gugudan(5);
gugudan.show();

"실행 화면 예시"와 같이 출력하는 코드를 완성하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		// 구구단 객체 생성 후 함수 호출
		Gugudan gugudan = new Gugudan(5);
		gugudan.show();
	}
}

// 이곳의 코드를 완성하세요
class Gugudan {
	int dan;
	public Gugudan(int d) {
		this.dan = d;
	}
	public void show() {
		for(int i=1; i<=9; i++) {
			System.out.println(this.dan + " x " + i + " = " + this.dan * i);
		}
	}
}
```
### 9/28(화) 도전문제 : 기본에 충실 + JavaFX 덧셈
#### 1.문자열 다루기
```
다음과 같은 String 문자열이 있습니다.
String a = "12345";
String b = "67890";

 ● a + b
 ● b - a
 ● a * b

문자열 a, b를 숫자로 바꾼 뒤 사칙연산을 계산하는 코드를 완성하세요.
```
```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		String a = "12345";
		String b = "67890";
		int iA = Integer.parseInt(a);
		int iB = Integer.parseInt(b);
			
		System.out.printf(
			"%d %d %d",
			(iA + iB),
			(iB - iA),
			(iA * iB)
		);
	}
}
```

#### 2.정사각형 출력하기
```
너비와 높이를 입력했을 때 
사각형을 출력하는 코드를 완성하세요.

※조건 : for문과 if-else을 사용하여 완성하세요.
```
```java
import java.io.*;
class Main {
	public static void main(String[] args) throws Exception {
		System.out.println("");
		int w = 12; // 너비
		int h = 7;  // 높이
		
		for(int i=1; i<=h; i++){
			for(int j=1; j<=w; j++) {
				if(i==1 || i==h) {
					System.out.print("*");
				} else {
					if(j==1 || j==w) {
						System.out.print("*");
					} else {
						System.out.print(" ");
					}
				}
			}
			System.out.println("");
		}
	}
}
```

#### 3.숫자를 입력받아 직각삼각형 출력하기
```
한변의 너비를 입력받아
해당 크기의 직각삼각형을 출력하는 프로그램을 완성하세요.

※ for문과 if-else문을 사용하세요.
```
```java
import java.io.*;
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int w = scn.nextInt();
		
		for(int i=1; i<=w; i++) {
			for(int j=1; j<=i; j++) {
				if(j==1 || j==i || i==w) {
					System.out.print("*");
				} else {
					System.out.print(" ");
				}
			}
			System.out.println("");
		}
	}
}
```

#### 4.오버로딩을 활용한 도형 넓이 구하기
```
함수 오버로딩(Overloading)을 이용하여 Shape 클래스를 완성하세요.

1.클래스명 : Shape

2.멤버 변수
 ● 초기값 PI = 3.141592 (final 로 선언하기)
3.멤버 함수
 ● area(int a) / 리턴타입 double
  원의 넓이 = 반지름 x 반지름 x PI
 ● area(int a, int b) / 리턴타입 double
  사각형의 넓이 = 가로 x 세로
 ● area(int a, int b, int c) / 리턴타입 double
  사다리꼴의 넓이 = (밑변 + 윗변) x 높이 x 0.5

각각의 메소드를 완성하여 다음 결과값을 구하세요.

 ● area(3)
 ● area(4, 5)
 ● area(3, 4, 7)
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		Shape shape = new Shape();
		System.out.printf(
			"%.2f %.2f %.2f",
			shape.area(3), shape.area(4, 5), shape.area(3,4,7)
		);
	}
}

class Shape {
	final double PI = 3.141593;
	double area(int a) {
		double da = (double) a;
		return da * da * PI;
	}
	double area(int a, int b) {
		double da = (double) a;
		double db = (double) b;
		return da * db;
	}
	double area(int a, int b, int c) {
		double da = (double) a;
		double db = (double) b;
		double dc = (double) c;
		return (da + db) * dc * 0.5;
	}
}
```
