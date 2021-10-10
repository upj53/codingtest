# 코딩테스트 답안
## 자바 2021년 2학기 도제반 방과후
### 9/13(월) 도전문제 : 구구단
1.구구단 출력 Level 1
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

2.구구단 출력 Level 2
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

3.구구단 출력 Level 3
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
