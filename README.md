# 미션 - 자동차 경주 게임
## Entire System
- 초기 입력받은 값을 바탕으로 자동차 생성 및 집합에 삽입
- 총 이동할 횟수 삽입 및 진행
- 진행 시에 각 차수별 자동차 거리 출력
- 모든 자동차들의 최대 이동 거리 구한 다음에 해당 자동차 이름 저장
- 최대 이동 거리에 해당하는 자동차들을 우승자로 출력

####Application
- 게임을 실행시키는 객체

####RacingGame
- 전체적인 게임을 다루는 객체
- 게임 세팅하는 Controller를 불러와 초기 게임 세팅하는 메서드
- 본 게임 진행하는 객체 불러오기
- 게임 결과를 출력하는 Controller를 불러오는 메서드

### Model
#### Car
- 초기 입력 받은 값으로 이름 저장.
- 한 턴 진행 시에 랜덤한 값을 바탕으로 전진 및 유지 판단, 결과 출력
- 최종 최대 거리와 부합하는지 판단

#### Cars
- 차들이 모여 있는 한 게임 세트를 의미
- 한 턴 진행하는 메서드
- 최대 거리를 구하는 메서드   
- 최종 우승자를 반환하는 메서드

### Viewer
#### InputViewer
- 초기 자동차 이름 값 입력시에 입력 메세지 송출 및 오류 시에 해당 에러 출력  
- 게임 진행 횟수 입력시에 입력 메세지 송출 및 오류 시에 해당 에러 출력  

#### OutputViewer
- 경주 시작시 이를 알리는 출력 메세지
- 각 자동차별 전진 횟수 출력 메세지
- 최종 우승자 알리는 메세지

### Controller
#### Initiator
- 초기 게임을 세팅하는 객체
- 초기에 사용자에게 이름 값들을 받아와서 게임을 세팅하는 값을 반환

#### ProcessGame
- 초기에 세팅한 값을 바탕으로 게임을 진행하는 객체
- 게임 진행 후에 값들 반환

#### EndGame
- 게임이 종료된 후, 누가 이겼는지를 계산하고 보여주는 객체
- 최대 거리 계산
- 최대 거리 바탕으로 우승자 찾기
- 우승자들 보여주기



## 🚀 기능 요구사항
- 주어진 횟수 동안 n대의 자동차는 전진 또는 멈출 수 있다.
- 각 자동차에 이름을 부여할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 이름은 5자 이하만 가능하다.
- 사용자는 몇 번의 이동을 할 것인지를 입력할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 random 값이 4 이상일 경우 전진하고, 3 이하의 값이면 멈춘다.
- 자동차 경주 게임을 완료한 후 누가 우승했는지를 알려준다. 우승자는 한 명 이상일 수 있다.

<br>

## ✍🏻 입출력 요구사항
### ⌨️ 입력
- 경주 할 자동차 이름(이름은 쉼표(,) 기준으로 구분)
```
pobi,woni,jun
```
- 시도할 회수
```
5
```

### 🖥 출력
- 각 차수별 실행 결과
```
pobi : --
woni : ----
jun : ---
```
- 단독 우승자 안내 문구
```
최종 우승자: pobi
```
- 공동 우승자 안내 문구
```
최종 우승자: pobi, jun
```
- 예외 상황 시 에러 문구를 출력해야 한다. 단, 에러 문구는 [ERROR] 로 시작해야 한다.
```
[ERROR] 시도 횟수는 숫자여야 한다.
```

### 💻 프로그래밍 실행 결과 예시
```
경주할 자동차 이름을 입력하세요.(이름은 쉼표(,) 기준으로 구분)
pobi,woni,jun
시도할 회수는 몇회인가요?
5

실행 결과
pobi : -
woni : 
jun : -

pobi : --
woni : -
jun : --

pobi : ---
woni : --
jun : ---

pobi : ----
woni : ---
jun : ----

pobi : -----
woni : ----
jun : -----

최종 우승자: pobi, jun
```

<br>

## 🎱 프로그래밍 요구사항
- 자바 코드 컨벤션을 지키면서 프로그래밍한다.
  - 기본적으로 [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)을 원칙으로 한다.
  - 단, 들여쓰기는 '2 spaces'가 아닌 '4 spaces'로 한다.
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메소드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메소드)가 한 가지 일만 하도록 최대한 작게 만들어라.
- 프로그래밍 요구사항에서 별도로 변경 불가 안내가 없는 경우 파일 수정과 패키지 이동을 자유롭게 할 수 있다.
- 예외 상황 시 에러 문구를 출력해야 한다. 단, 에러 문구는 `[ERROR]` 로 시작해야 한다.

### 추가된 요구사항
- 함수(또는 메소드)의 길이가 15라인을 넘어가지 않도록 구현한다.
  - 함수(또는 메소드)가 한 가지 일만 잘 하도록 구현한다.
- else 예약어를 쓰지 않는다.
  - 힌트: if 조건절에서 값을 return하는 방식으로 구현하면 else를 사용하지 않아도 된다.
  - else를 쓰지 말라고 하니 switch/case로 구현하는 경우가 있는데 switch/case도 허용하지 않는다.

### 프로그래밍 요구사항 - Application
- Application 클래스를 활용해 구현해야 한다.
- Application의 패키지 구조와 구현은 변경하지 않는다.
- `final Scanner scanner = new Scanner(System.in);`는 변경하지 않는다.
- `// TODO 구현 진행` 이 후 부터 구현한다.

```java
public class Application {
    public static void main(String[] args) {
        final Scanner scanner = new Scanner(System.in);
        // TODO 구현 진행
    }
}
```

### 프로그래밍 요구사항 - RandomUtils
- RandomUtils 클래스를 활용해 랜덤 기능을 구현해야 한다.
- RandomUtils의 패키지 구조와 구현은 변경하지 않는다.

```java
private static final Random RANDOM = new Random();
    private RandomUtils() {
    }
    public static int nextInt(final int startInclusive, final int endInclusive) {
    ...
```

### 프로그래밍 요구사항 - Car 객체
- 다음 Car 객체를 활용해 구현해야 한다.
- Car 기본 생성자를 추가할 수 없다.
- name, position 변수의 접근 제어자인 private을 변경할 수 없다.
- 가능하면 setPosition(int position) 메소드를 추가하지 않고 구현한다.

```java
public class Car {
    private final String name;
    private int position = 0;

    public Car(String name) {
        this.name = name;
    }

    // 추가 기능 구현
}
```

<br>

## 📈 진행 요구사항
- 미션은 [java-racingcar-precourse 저장소](https://github.com/woowacourse/java-racingcar-precourse) 를 fork/clone해 시작한다.
- 기능을 구현하기 전에 java-racingcar-precourse/docs/README.md 파일에 구현할 기능 목록을 정리해 추가한다.
- git의 commit 단위는 앞 단계에서 README.md 파일에 정리한 기능 목록 단위로 추가한다.
  - [AngularJS Commit Message Conventions](https://gist.github.com/stephenparish/9941e89d80e2bc58a153) 참고해 commit log를 남긴다.
- [프리코스 과제 제출 문서](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse) 절차를 따라 미션을 제출한다.
  - [프리코스 과제 FAQ](https://github.com/woowacourse/woowacourse-docs/tree/master/precourse/faq) 문서를 참고하여 진행할 수 있다.

<br>

## 📝 License

This project is [MIT](https://github.com/woowacourse/java-racingcar-precourse/blob/master/LICENSE) licensed.
