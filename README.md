# 코딩테스트 솔루션
## 자바 2021년 2학기 예비도제반 방과후 수업
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

### 10/6(수) 도전문제 : 코딩감각 살리기 1
#### 1.1부터 100까지 3의 배수와 7의 배수의 합 구하기
```
1부터 100까지의 숫자 중에서

3의 배수와 7의 배수의 합을 구하시오.

※ for문과 if문을 사용하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		int total = 0;
		for(int i=1; i<=100; i++) {
			if(i%3==0 || i%7==0) {
				total += i;
			}
		}
		System.out.println(total);
	}
}
```
#### 2.1부터 1000까지 특정수의 배수의 개수
```
숫자를 하나 입력받으세요.

1부터 1000까지의 숫자 중에서 입력받은 숫자의 배수가 몇개 있는지 구하세요.

예를들어 2을 입력하면 500이 나오는데
1부터 1000까지 2의 배수는 500개가 있음을 알 수 있다.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int input = scn.nextInt();
		int cnt = 0;
		for(int i=1; i<=1000; i++) {
			if(i%input == 0) {
				cnt ++;
			}
		}
		System.out.println(cnt);
	}
}
```

#### 3.윤년/평년 구하는 함수 만들기
```
1.먼저 연도를 입력받으세요.

2.다음 조건을 모두 만족하면 윤년입니다.
  ① 연도를 4로 나누어 떨어져야 함
  ② 연도를 100으로나누어 떨어지지 않거나
      연도를 400으로 나누어 떨어져야 함

3.윤년일 때 "윤년", 평년일 때 "평년"을 출력하세요.

※ 두 함수(isYoon1, isYoon2)를 만들고 완성하세요.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int input = scn.nextInt();
		
		if(isYoon1(input) && isYoon2(input)) {
			System.out.println("윤년");
		} else {
			System.out.println("평년");
		}
	}
	static boolean isYoon1(int y) {
		if(y % 4 == 0) return true;
		else return false;
	}
	static boolean isYoon2(int y) {
		if(y % 100 != 0 || y % 400 == 0) return true;
		else return false;
	}
}
```

#### 4.삼각형 높이를 입력받아 *로 삼각형 그리기
```
1.삼각형 높이를 입력받습니다.

2.입력받은 높이를 가진 삼각형을 출력하세요.

예를들어 3을 입력받으면 높이가 3인 삼각형입니다.

  *

 ***

*****

4를 입력받으면 높이가 4인 삼각형입니다.

   *

  ***

 *****

*******

규칙을 찾아내보세요 :)
```
```java
import java.util.Scanner; 
class Main { 
	public static void main(String[] args) {
		Scanner s=new Scanner(System.in); 
		int n=s.nextInt();
		
		for(int i=0; i<n; i++) { 
			for(int j=1; j<n-i; j++) { 
				System.out.print(" "); 
			} 
			for(int k=0; k<i*2+1; k++) { 
				System.out.print("*"); 
			} 
			System.out.println(); 
		}
	} 
}
```
### 10/8(금) 도전문제 : 코딩감각 살리기 2
#### 1. 입력받은 세 숫자의 합과 평균 구하기
```
다음은 세 숫자를 입력받는 방법입니다.

● int a = scn.nextInt();
● int b = scn.nextInt();
● int c = scn.nextInt();

입력받은 세 숫자의 합과 평균을 구한 후 합과 평균을 구하세요.
합은 정수로 출력하고,
평균을 구한 후에는 소수점 둘째자리까지 출력하세요.

※ (힌트) int 자료형을 double 자료형으로 변환하세요.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int a = scn.nextInt();
		int b = scn.nextInt();
		int c = scn.nextInt();
		double total = (double) (a + b + c);
		double average = total / 3;
		
		System.out.printf("%d %.2f", (a+b+c), average);
	}
}
```

#### 2. for문을 이용한 제곱승 구하기
```
두 숫자를 입력받아 for문을 이용해서 제곱승을 구하세요.

예를들어 3과 2를 입력받았다면
3의 2승의 값, 즉 9를 for문으로 계산해서 출력하면 됩니다.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int x = scn.nextInt();
		int y = scn.nextInt();
		int result = 1;
		
		for(int i=0; i<y; i++) {
			result *= x;
		}
		
		System.out.println(result);
	}
}
```

#### 3. 369게임
```
숫자를 입력받아 3의 배수는 X로 출력하세요.

예를들어 10을 입력받았다면
1 2 X 4 5 X 7 8 X 10
이렇게 출력하세요.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int input = scn.nextInt();
		
		for(int i=1; i<=input; i++) {
			if(i % 3 == 0) {
				System.out.print("X");
			} else {
				System.out.print(i);
			}
			if(i != input) System.out.print(" ");
		}
	}
}
```

#### 4. 덧셈/뺄셈/곱셈/나눗셈 함수 만들기
```
Number 클래스를 완성하여
입력받은 두 숫자에 대해

● 덧셈 : add(숫자1, 숫자2) → 정수 리턴
● 뺄셈 : sub(숫자1, 숫자2) → 정수 리턴
● 곱셈 : mul(숫자1, 숫자2) → 정수 리턴
● 나누기의 몫 : div(숫자1, 숫자2) → 정수 리턴
● 나누기의 나머지 : rest(숫자1, 숫자2) → 정수 리턴 

를 구하는 함수를 완성하세요.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int a = scn.nextInt();
		int b = scn.nextInt();
		Number number = new Number();
		
		System.out.printf(
			"%d %d %d %d %d",
			number.add(a, b),
			number.sub(a, b),
			number.mul(a, b),
			number.div(a, b),
			number.rest(a, b)
		);
	}
}

class Number {
	public int add(int a, int b) {
		return (a+b);
	}
	public int sub(int a, int b) {
		return (a-b);
	}
	public int mul(int a, int b) {
		return (a*b);
	}
	public int div(int a, int b) {
		return (a/b);
	}
	public int rest(int a, int b) {
		return (a%b);
	}
}
```

### 10/18(월) 도전문제 : 코딩감각 살리기 3
#### 1.성적에 따른 학점 출력하기 (일반함수사용)
```
국어, 영어, 수학 점수를 입력받고 평균을 구하여 리턴하는 함수를 만드세요.

그 후 결과값에 따라 학점을 A, B, C, D, F 로 출력하세요.

점수에 따른 학점분포는 다음과 같습니다.

● 90 ＜ 점수 ≤ 100 → A
● 80 ＜ 점수 ≤ 90 → B
● 70 ＜ 점수 ≤ 80 → C
● 60 ＜ 점수 ≤ 70 → D
● 0 ≤ 점수 ≤ 60 → E

※ if-else if문을 사용하여 학점을 출력하세요.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int kor = scn.nextInt();
		int eng = scn.nextInt();
		int mat = scn.nextInt();
		
		System.out.println(
			getAverage(kor, eng, mat)	
		);
	}
	
	static char getAverage(int k, int e, int m) {
		double total = (double) (k+e+m);
		double average = total / 3.0;
		if(average > 90 && average <= 100) {
			return 'A';
		} else if(average > 80 && average <= 90) {
			return 'B';
		} else if(average > 70 && average <= 80) {
			return 'C';
		} else if(average > 60 && average <= 70) {
			return 'D';
		} else if(average > 0 && average <= 60) {
			return 'F';
		} else {
			return '-';
		}
	}
}
```

#### 2.성적에 따른 학점 출력하기 (클래스사용)
```
자바 4-1.문제를 클래스를 사용하여 재구성하세요.
클래스의 특징은 다음과 같습니다.

● 멤버변수
  - kor 국어 (int)
  - eng 영어 (int)
  - mat 수학 (int)

● 생성자
  생성자에서 Scanner 로 국어 영어 수학점수를 받은후
  멤버변수(kor, eng, mat)에 저장하세요.

● 멤버함수 : getAverage(국어점수, 영어점수, 수학점수)
  90 ＜ 점수 ≤ 100 → A
  80 ＜ 점수 ≤ 90 → B
  70 ＜ 점수 ≤ 80 → C
  60 ＜ 점수 ≤ 70 → D
  0 ≤ 점수 ≤ 60 → E

● 멤버함수 : run()
  run() 을 실행시키면 평균점수에 따라 학점을 출력하도록 하세요.
  학점을 구할 때는 getAverage() 함수를 사용하세요.
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Hakjum hakjum = new Hakjum();
		hakjum.run();	
	}
}

// 클래스를 완성하세요
class Hakjum {
	int kor;
	int eng;
	int mat;
	public Hakjum() {
		Scanner scn = new Scanner(System.in);
		this.kor = scn.nextInt();
		this.eng = scn.nextInt();
		this.mat = scn.nextInt();
		scn.close();
	}
	public void run() {
		System.out.println(
			this.getAverage()
		);
	}
	public char getAverage() {
		int k = this.kor;
		int e = this.eng;
		int m = this.mat;
		double total = (double) (k+e+m);
		double average = total / 3.0;
		if(average > 90 && average <= 100) {
			return 'A';
		} else if(average > 80 && average <= 90) {
			return 'B';
		} else if(average > 70 && average <= 80) {
			return 'C';
		} else if(average > 60 && average <= 70) {
			return 'D';
		} else if(average > 0 && average <= 60) {
			return 'F';
		} else {
			return '-';
		}
	}
}
```

#### 3.너비를 입력받아 다이아몬드 모양(*) 출력하기
```
너비를 입력받아 다이아몬드 모양을 출력하세요.

예를들어 너비가 3일 경우

  *
 * *
* * *
 * *
  *

이런 다이아몬드 모양이 출력됩니다.

● printDimond함수를 완성하세요
  리턴 없음
  파라미터 w 너비 (정수)

※ 힌트
  다이아몬드 위쪽 삼각형(▲)을 먼저 출력하고 아래쪽 삼각형(▼)을 출력하세요 :)
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int width = scn.nextInt();
		printDimond(width);
		scn.close();
	}
	// printDimond 함수를 완성하세요
	static void printDimond(int w) {
		for(int i=0; i<w; i++) {
			for(int j=1; j<w-i; j++) {
				System.out.print(" ");
			}
			for(int k=0; k<i*2+1; k++) {
				System.out.print("*");
			}
			System.out.println("");
		}
		for(int i=w-2; i>=0; i--) {
			for(int j=1; j<w-i; j++) {
				System.out.print(" ");
			}
			for(int k=0; k<i*2+1; k++) {
				System.out.print("*");
			}
			System.out.println("");
		}
	}
}
```
### 10/19(월) 도전문제 : 객체지향(OOP)과 친해지기 1
#### 1. 객체지향 생성자 만들기
```
클래스에서 생성자는 객체를 new 로 생성한 동시에 실행하는 함수를 말합니다.

생성자 함수의 파라미터는 아무것도 없을 수 있고,
상황에 따라 여러개의 파라미터를 넘겨받을 수 있습니다.

다음 Person 클래스에서 이름과 생년월일 파라미터를 넘겨주는 클래스를 작성하세요.

(예) Person 생성자

● 이름 : 김성일
● 생년월일 : 2021년 7월 12일

(출력)

김성일(2021-7-12)

위와 같이 출력하는 생성자 함수를 완성하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		Person person = new Person("김성일", 2021, 7, 12);
		System.out.printf(
			"%s(%d-%d-%d)",
			person.name, person.year, person.month, person.day
		);
	}
}

class Person {
	// 생성자 함수를 완성하세요
	String name;
	int year;
	int month;
	int day;
	public Person(String n, int y, int m, int d) {
		this.name = n;
		this.year = y;
		this.month = m;
		this.day = d;
	}
}
```

#### 2. 객체지향 생성자 오버로딩
```
함수 오버로딩은 함수 이름은 동일하지만 파라미터가 다를 때 사용할 수 있습니다.

예를들어

● 파라미터 : 없음
● 파라미터 : "이름"
● 파라미터 : "이름", "나이"
● 파라미터 : "이름", "태어난 해", "태어난 달", "태어난 날"

다음과 같은 4종류의 생성자를 이름은 같지만 파라미터를 다르게 해서 만들 수 있습니다.
이는 생성자 뿐 아니라 객체에 사용하는 모든 함수에도 동일하게 적용됩니다.

클래스 Person에 위의 의 4가지 종류의 생성자를 만든 후,
각 생성자에서 해당 정보를 출력하는 기능을 구현하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		Person person1 = new Person();
		Person person2 = new Person("둘리");
		Person person3 = new Person("둘리", 39);
		Person person4 = new Person("둘리", 1983, 4, 22);
	}
}

class Person {
	// 생성자 함수를 완성하세요
	public Person() {
		System.out.println("생성자");
	}
	public Person(String name) {
		System.out.printf(
		"%s\n",
		name
		);
	}
	public Person(String name, int age) {
		System.out.printf(
		"%s(%d세)\n",
		name, age
		);
	}
	public Person(String name, int year, int month, int day) {
		System.out.printf(
		"%s(%d-%d-%d)\n",
		name, year, month, day
		);
	}
}
```

#### 3.try-catch문으로 에러 핸들링하기
```
어떤 숫자를 0으로 나눌 수 없습니다.
try-catch문을 사용해서 0으로 나눌 경우에 프로그램이 에러로 종료되지 않고
"ERROR" 메시지를 출력하도록 하세요.

에러가 안날 경우는 a를 b 로 나누기의 몫과 나머지를 출력하세요.

예를들어 10을 3으로 나누면 몫은 3이고 나머지는 1입니다
하지만 10을 0으로 나누면 ERROR 를 출력합니다.
```
```java
import java.io.*;
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		int a = scn.nextInt();
		int b = scn.nextInt();
		try {
			System.out.printf("%d %d", a/b, a%b);
		} catch(Exception e) {
			System.out.println("ERROR");
		}
		scn.close();
	}
}
```
