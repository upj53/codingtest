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
### 10/26(화) 도전문제 : 객체지향(OOP)과 친해지기 2
#### 1. 객체지향 함수 오버로딩 (출력함수)
```
print 함수를 함수 오버로딩을 사용하여 만들려고 합니다.

다음과 같은 파라미터의 종류가 있을 때 print() 함수를 객체지향 클래스로 구성하세요.

1.파라미터 없음
2.파라미터 1개 : 정수(int)
3.파라미터 1개 : 문자열(String)
4.파라미터 2개 : 실수, 소수점자리수(double, int)
   → 실수를 소수점 몇자리까지 표기하라는 말입니다.

위와 같은 특성을 갖는 print() 함수를 PrintOOP 클래스에 작성하세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		PrintOOP prt1 = new PrintOOP();
		PrintOOP prt2 = new PrintOOP();
		PrintOOP prt3 = new PrintOOP();
    PrintOOP prt4 = new PrintOOP();
    PrintOOP prt5 = new PrintOOP();
    
    prt1.print();
    prt2.print(7);
    prt3.print("자바생성자");
    prt4.print(3.141592, 2);
    prt5.print(3.141592, 5);
	}
}

class PrintOOP {
  public void print() {
    System.out.printf("print함수\n");
  }
  public void print(int a) {
    System.out.printf("정수:%d\n", a);
  }
  public void print(String b) {
    System.out.printf("문자열:%s\n", b);
  }
  public void print(double c, int d) {
    String str = "실수:%."+d+"f\n";
    System.out.printf(str, c);
  }
}
```

#### 2. 객체지향 상속 1
```
LoL(리그 오브 레전드) 게임의 캐릭터를 자바 클래스를 사용하여 설계하려고 합니다.

다음과 같이 챔피온을 구성하려고 할 때 어떻게 클래스를 구성하면 될까요?

● 암살자 : 녹턴
● 전사  : 가렌
● 마법사 : 아리
● 원거리딜러 : 카이사
● 서포터 : 라칸
● 탱커 : 자크

객체지향의 상속을 사용해서 LoL 클래스와 Champion 클래스를 완성해보세요.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		Champion chmp1 = new Champion("녹턴", "암살자", 9, 3, 3);
		Champion chmp2 = new Champion("가렌", "전사", 6, 2, 6);
		Champion chmp3 = new Champion("아리", "마법사", 8, 4, 7);
		Champion chmp4 = new Champion("카이사", "원거리딜러", 8, 4, 4);
		Champion chmp5 = new Champion("라칸", "서포터", 9, 0, 5);
		Champion chmp6 = new Champion("자크", "탱커", 1, 10, 2);
		
		chmp1.print();
		chmp2.print();
		chmp3.print();
		chmp4.print();
		chmp5.print();
		chmp6.print();
	}
}

class LoL {
	String name;
	public LoL(String _name) {
		this.name = _name;
	}
}

class Champion extends LoL {
	String role;
	int K;
	int D;
	int A;
	public Champion(String _name, String _role, int _k, int _d, int _a) {
		super(_name);
		this.role = _role;
		this.K = _k;
		this.D = _d;
		this.A = _a;
	}
	public void print() {
		System.out.printf(
			"%s(%s)%d/%d/%d\n",
			super.name, this.role, this.K, this.D, this.A
		);
	}
}
```

#### 3. 객체지향 상속 2 (enum 활용)
```
"자바 6-1. 객체지향 상속 1"을 통해 만들어진 객체에서 챔피온의 역할을 문자열(String)을 사용하여 구성했습니다.

해당 클래스를 enum을 활용하여 업그레이드 해보겠습니다.
enum 클래스는 열거체를 나타낼 때 사용하는 방법으로 코드의 가독성을 높여주는 편리한 기능입니다.

(enum 사용법)
enum  열거체이름  {상수1이름,  상수2이름,  ...  }

(enum 예제)
enum  Weekday  {Sun, Mon, Tue, Wed, Thu, Fri, Sat}

Weekday.Sun
Weekday.Mon
Weekday.Tue
...

enum을 활용하여 챔피온의 역할을 다음과 같이 지정하고,
LoL 클래스에 CS속성을 추가하여 클래스를 완성하세요.

역할(Role)
● 암살자 : Slayer
● 전사 : Fighter
● 마법사 : Mage
● 원거리딜러 : Marksman
● 서포터 : Controller
● 탱커 : Tank
```
```java
enum Role {
	Slayer, Fighter, Mage, Marksman, Controller, Tank
}

class Main {
	public static void main(String[] args) throws Exception {
		Champion chmp1 = new Champion("녹턴", Role.Slayer, 9, 3, 3, 53);
		Champion chmp2 = new Champion("가렌", Role.Fighter, 6, 2, 6, 43);
		Champion chmp3 = new Champion("아리", Role.Mage, 8, 4, 7, 92);
		Champion chmp4 = new Champion("카이사", Role.Marksman, 8, 4, 4, 68);
		Champion chmp5 = new Champion("라칸", Role.Controller, 9, 0, 5, 35);
		Champion chmp6 = new Champion("자크", Role.Tank, 1, 10, 2, 29);
		
		chmp1.print();
		chmp2.print();
		chmp3.print();
		chmp4.print();
		chmp5.print();
		chmp6.print();
	}
}

class LoL {
	String name;
	int CS;
	public LoL(String _name, int _cs) {
		this.name = _name;
		this.CS = _cs;
	}
}

class Champion extends LoL {
	Role role;
	int K;
	int D;
	int A;
	public Champion(String _name, Role _role, int _k, int _d, int _a, int _cs) {
		super(_name, _cs);
		this.role = _role;
		this.K = _k;
		this.D = _d;
		this.A = _a;
	}
	public void print() {
		System.out.printf(
			"%s(%s)[%d]%d/%d/%d\n",
			super.name, this.role, super.CS, this.K, this.D, this.A
		);
	}
}
```

### 11/2(화) 도전문제 : 객체지향(OOP)과 친해지기 3
#### 1.추상 클래스 (스타크래프트 유닛 생성하기)
```
추상 클래스란? [교안 PPT 68페이지를 참고하세요]

구체적으로 구현하지 않은 클래스
상속받은 클래스에서 구체적으로 구현해야할 의무가 있다
단, 추상 클래스는 구현하지 않는다
문제) 스타크래프트 종족별 일꾼 만들기

Worker(일꾼) 클래스를 추상클래스로 만드세요
-일꾼은 미네랄을 캐고(getMineral)
-가스를 채취합니다(getGas)
-각 함수를 구현하고 일을 시켜보세요(work)
각 종족별로 Worker(일꾼) 클래스를 상속받은 클래스를 만드세요
ZergWorker(저그)
TerranWorker(테란)
ProtossWorker(프로토스)
메인함수의 클래스에서 저그, 테란, 프로토스의 일꾼을 생성하세요
```
```java
import java.util.Scanner;
class Main {
	public static void main(String[] args) throws Exception {
		Scanner scn = new Scanner(System.in);
		ZergWorker zergWorker = new ZergWorker();
		TerranWorker terranWorker = new TerranWorker();
		ProtossWorker protossWorker = new ProtossWorker();
		
		zergWorker.work();
		terranWorker.work();
		protossWorker.work();
	}
}

abstract class Worker {
	public abstract void getMineral();
	public abstract void getGas();
	public abstract void work();
}

class ZergWorker extends Worker {
	@Override
	public void getMineral() {
		System.out.println("저그:미네랄을 채취합니다");
	}
	@Override
	public void getGas() {
		System.out.println("저그:가스를 채취합니다");
	}
	@Override
	public void work() {
		this.getMineral();
		this.getGas();
	}
}

class TerranWorker extends Worker {
	@Override
	public void getMineral() {
		System.out.println("테란:미네랄을 채취합니다");
	}
	@Override
	public void getGas() {
		System.out.println("테란:가스를 채취합니다");
	}
	@Override
	public void work() {
		this.getMineral();
		this.getGas();
	}
}

class ProtossWorker extends Worker {
	@Override
	public void getMineral() {
		System.out.println("프로토스:미네랄을 채취합니다");
	}
	@Override
	public void getGas() {
		System.out.println("프로토스:가스를 채취합니다");
	}
	@Override
	public void work() {
		this.getMineral();
		this.getGas();
	}
}
```

#### 2.인터페이스 (스타크래프트 유닛 설계하기)
```
인터페이스란 [교안 PPT 76페이지 참고]

클래스 혹은 프로그램이 제공하는 기능을 명시적으로 선언한다
추상 메서드와 상수로만 이루어져 있다
구현 코드가 없기 때문에 인스턴스를 생성할 수 없다
스타크래프트 게임은 세 종족(저그, 테란, 프로토스)이 유닛을 생산하여 전투하는 전략 시뮬레이션 게임입니다. 자바의 인터페이스를 활용하여 아래 조건에 맞게 유닛을 설계하세요.

모든 종족의 유닛은 Unit 클래스를 구현해야 합니다.
-create() 함수 : 생성됐을 때 호출되는 함수
-remove() 함수 :  소멸 됐을 때 호출되는 함수
공격유닛(AttackUnit)은 각 종족의 기본 공격 유닛을 설계할 때 사용합니다. 공격유닛에는 저그는 히드라, 테란은 마린, 프로토스는 드래곤이 있습니다.
-max_energy  상수 : 공격유닛은 최대 에너지값(30)이 있습니다.
-attack() 함수 : 공격을 구현하는 함수입니다.
-getDemage(int dmg) : 공격을 받았을 때 dmg 만큼의 데미지를 입으며 에너지 에서 값이 깎입니다.
각 종족의 공격유닛에 대한 클래스를 구현하세요. 모든 공격유닛은 Unit, AttackUnit을 구현해야 합니다.
-Hydra (저그)
-Marin (테란)
-Dragon (프로토스)
Hydra, Marin, Dragon 클래스는 다음의 특징을 같습니다.
-isAlive 불린값 : 살아 있는지 죽어 있는지 체크
-energy 정수 : 남아 있는 에너지 체크
-공격을 받아서 에너지가 0보다 작아지면 자동소멸됩니다.
```
```java
class Main {
	public static void main(String[] args) throws Exception {
		Hydra hydra = new Hydra();
		Marin marin = new Marin();
		Dragon dragon = new Dragon();
		
		// 히드라 유닛
		hydra.create();
		hydra.attack();
		hydra.getDemage(10);
		hydra.getDemage(10);
		hydra.getDemage(10);
		hydra.getDemage(10);
		hydra.getDemage(10);
		
		// 마린 유닛
		marin.create();
		marin.attack();
		marin.getDemage(25);
		marin.getDemage(25);
		marin.getDemage(25);
		
		// 드래곤 유닛
		dragon.create();
		dragon.attack();
		dragon.getDemage(5);
		dragon.getDemage(5);
		dragon.getDemage(5);
		dragon.getDemage(5);
		dragon.getDemage(5);
	}
}

interface Unit {
	void create();
	void remove();
}

interface AttackUnit {
	int max_energy = 30;
	void attack();
	void getDemage(int dmg);
}

class Hydra implements Unit, AttackUnit {
	boolean isAlive = false;
	int energy = 0;
	
	@Override
	public void create() {
		isAlive = true;
		energy = max_energy;
		System.out.println("히드라:생성되었습니다.에너지:"+energy);
	}
	@Override
	public void remove() {
		isAlive = false;
		System.out.println("히드라:소멸되었습니다");
	}
	@Override
	public void attack() {
		System.out.println("히드라:공격합니다");
	}
	@Override
	public void getDemage(int dmg) {
		if(isAlive && energy > 0) {
			energy -= dmg;
			System.out.println("히드라:공격받았습니다.에너지:"+energy);
			if(energy <= 0) {
				this.remove();
			}
		}
	}
}

class Marin implements Unit, AttackUnit {
	boolean isAlive = false;
	int energy = 0;
	
	@Override
	public void create() {
		isAlive = true;
		energy = max_energy;
		System.out.println("마린:생성되었습니다.에너지:"+energy);
	}
	@Override
	public void remove() {
		isAlive = false;
		System.out.println("마린:소멸되었습니다");
	}
	@Override
	public void attack() {
		System.out.println("마린:공격합니다");
	}
	@Override
	public void getDemage(int dmg) {
		if(isAlive && energy > 0) {
			energy -= dmg;
			System.out.println("마린:공격받았습니다.에너지:"+energy);
			if(energy <= 0) {
				this.remove();
			}
		}
	}
}

class Dragon implements Unit, AttackUnit {
	boolean isAlive = false;
	int energy = 0;
	
	@Override
	public void create() {
		isAlive = true;
		energy = max_energy;
		System.out.println("드래곤:생성되었습니다.에너지:"+energy);
	}
	@Override
	public void remove() {
		this.isAlive = false;
		this.energy = 0;
		System.out.println("드래곤:소멸되었습니다");
	}
	@Override
	public void attack() {
		System.out.println("드래곤:공격합니다");
	}
	@Override
	public void getDemage(int dmg) {
		if(isAlive && energy > 0) {
			energy -= dmg;
			System.out.println("드래곤:공격받았습니다.에너지:"+energy);
			if(energy <= 0) {
				this.remove();
			}
		}
	}
}
```
