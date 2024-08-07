# 프로세스와 스레드의 개념

## 프로그램과 프로세스

프로세스와 스레드 둘을 한마디로 정의하자면 다음과 같다.

▪**프로세스**: 운영체제로부터 자원을 할당받은 **작업의 단위**.

▪**스레드**: 프로세스가 할당받은 자원을 이용하는 **실행 흐름의 단위**.

---

### 정적 프로그램 (Static Program)

프로그램은 **파일이 저장 장치에 저장되어 있지만 메모리에는 올라가 있지 않은 정적인 상태** 를 말한다.

![1](https://github.com/user-attachments/assets/591621eb-9661-49da-af5a-1744bafdc03b)

윈도우에서는 보통 `.exe` 파일이나 Mac의 `.dmg` 파일과 같은 컴퓨터에서 실행할 수 있는 파일을 통칭한다. 

- 예를 들면 엑셀, 웹 브라우저(크롬, 엣지, 웨일 등), 카카오톡 등

단, 아직 파일을 실행하지 않은 상태이기 때문에 정적 프로그램(Static Program)을 줄여서 프로그램(Program)이라고 부른 것이다.

- 쉽게 말해서 그냥 **코드 덩어리**다.

### 프로세스(Process)

프로그램이 코드 덩어리라면, **프로세스는**  컴퓨터에서 실행 중인 프로그램을 말한다.

- **프로그램을 실행 시켜 정적인 프로그램이 동적(動的)으로  변하여 프로그램이 돌아가고 있는 상태를 말한다**. 즉, 컴퓨터에서 작업 중인 프로그램을 의미하는 것이다.

![1](https://github.com/user-attachments/assets/96cf6d42-0767-4888-b7ce-12fb11a6d535)

모든 프로그램을 실행하게 되면 운영체제에 의해 파일은 컴퓨터 메모리(RAM)에 올라가게 되고, 운영체제로부터 시스템 자원(CPU)를 할당 받아 동작하게 된다.

- 프로그램이 실행되는 동안 운영체제로부터 시스템 자원(CPU 및 메모리)을 할당 받아 동작한다.

그래서 프로그램을 실행하는 순간 파일은 컴퓨터 메모리에 올라가게 되고, 운영체제로부터 시스템 자원(CPU)을 할당 받아 프로그램 코드를 실행시켜 우리가 서비스를 이용할 수 있게 되는 것이다.

---

## 프로세스와 스레드

### 프로세스의 한계

과거에는 프로그램이 하나의 프로세스로 실행되었지만, 프로그램이 복잡해지면서 단일 프로세스로는 효율적인 처리가 어려워졌다.

- 프로그램 하나가 단순히 한 가지 작업만을 하는 경우는 없기 떄문에.

운영체제는 안전성을 위해서 각 프로세스가 자신에게 할당된 메모리 내의 정보에만 접근할 수 있도록 제약을 둔다. 

- 이렇게 함으로써 각 프로세스가 독립적으로 동작하며, 하나의 프로세스가 다른 프로세스의 메모리 영역에 접근하여 데이터를 손상시키는 것을 방지한다.

"동일한 프로그램을 처리하기 위한 프로세스를 여러 개 만들면 되지 않을까?" 생각을 할 수도 있지만 

이러한 제약 때문에 여러 프로세스로 나누는 방법은 불가능한 일이었고 이 문제를 해결하기 위해 **스레드**라는 더 작은 실행 단위가 도입되었다.

- 동일한 프로그램을 여러 개의 프로세스로 만들게 되면, 각 프로세스는 독립적인 메모리 공간을 가지기 때문에 메모리 사용량이 증가하고, CPU 자원의 할당도 중복되어 비효율적이다.

---

### 스레드(Thread)

스레드란, 하나의 **프로세스 내에서 동시에 진행되는 작업 갈래, 흐름의 단위** 를 말한다.

이해하기 쉽게 비유를 들자면, 크롬 브라우저가 실행 되면 프로세스 하나가 생성될 것이다. 그런데 우리는 브라우저에서 파일을 다운 받으며 온라인 쇼핑을 하면서 게임을 하기도 한다.

![1](https://github.com/user-attachments/assets/4f68f874-097c-4d71-b6dc-8d5b0dcaa5bb)

즉, 하나의 프로세스 안에서 여러가지 작업들 흐름이 동시에 진행되기 때문에 가능한 것인데, 이러한 일련의 작업 흐름들을 스레드라고 하며 여러개가 있다면 이를 멀티(다중) 스레드 라고 부른다.

![1](https://github.com/user-attachments/assets/0a3e4db6-42a9-481a-aa45-e2324258ce01)

보통 프로그램은 하나 이상의 프로세스를 가지고 있고, 모든 프로세스는 최소 하나의 스레드(메인 스레드)를 가지고 있습니다. 추가적인 작업을 위해 새로운 스레드를 생성하여 병렬 작업을 수행할 수 있다.

- 스레드는 프로세스와 다르게 동일한 프로세스 내에서 실행되며, 프로세스의  메모리를 공유하며 작동한다.
- 프로세스 내의 각 스레드는 독립적인 실행 흐름을 가지므로, 마치 여러 함수가 병렬로 실행되는 것처럼 볼 수 있습니다.
- 일반적으로 프로그램이 시작될 때 실행되는 메인 함수도 메인 스레드로 볼 수 있습니다. 다른 스레드는 이 메인 스레드에서 파생됩니다.

---

# 프로세스와 스레드의 메모리

## 프로세스의 자원 구조

![2](https://github.com/user-attachments/assets/61abc61a-8583-470d-b7b3-6778d5b10000)

**코드 영역(Code / Text) :** 

프로그래머가 작성한 프로그램 함수들의 코드가 CPU가 해석 가능한 기계어 형태로 저장되어 있다.

- 프로그램이 실행될 때 코드가 로드되고, 일반적으로 읽기 전용이다.

**데이터 영역(Data)** : 

프로그램이 실행되면서 사용하는 전역 변수나 static 변수가 저장되어 있다. 데이터 영역은 크게 .data , .rodata, .bss 영역으로 나뉜다.

- **.data :** 초기값이 있는 전역 변수와 static 변수가 저장되는 영역 (`int init= 10`;)
- **.BSS** : 초기값이 없는 전역 변수와 static 변수가 저장되는 영역 (`int init;`)
- **.rodata** : 읽기 전용 데이터(read-only data)가 저장되는 영역입니다. 주로 상수(const)와 문자열 상수 등이 이곳에 저장된다. (`const int constantVar = 100;`, `const char *str = "Hello, World!`

**스택 영역(Stack) :** 

함수 호출 시 지역 변수, 매개변수, 반환 주소 등을 저장하는 임시적인 공간이다.

- 함수 호출 시 새로운 스택 프레임이 생성되어 해당 함수의 지역 변수와 호출 정보를 저장한다. 함수가 종료되면 이 스택 프레임은 제거된다.
- Stack은 함수의 호출과 함께 할당되며, 함수의 호출이 완료되면 소멸한다. 만일 stack 영역을 초과하면 stack overflow 에러가 발생한다.

**힙 영역(Heap) :** 

동적으로 메모리를 할당하고 해제할 수 있는 공간이다. 주로 객체, 인스턴스, 동적으로 생성된 배열 등의 데이터가 이 영역에 저장된다.

- 메모리 할당은 프로그래머가 명시적으로 처리하거나, 자동 메모리 관리(예: 가비지 컬렉터)가 처리한다.

스택 영역(Stack)과 힙 영역(Heap)은 프로세스가 실행되는 동안 크기가 변경되는 동적 영역이다.

- 스택 영역은 **동적으로 크기가 변하지만 유한한 크기를 가진 영역이다.**
- 반대로 코드 영역(Code)과 데이터 영역(Data)은 선언 시 크기가 결정되는 정적 영역이다.

## 스레드의 자원 공유

동일한 프로세스에 속하는 스레드끼리는 프로세스의 자원을 공유하기 때문에 프로세스의 실행 흐름의 일부가 될 수 있다.

![1](https://github.com/user-attachments/assets/9ae8baf5-9a2b-4e07-abb9-fc4ec41cb937)

스레드는 Code/Data/Heap 형식으로 할당된 메모리 영역을 공유하고 독립적으로 Stack 영역을 할당 받아  공유하지 않는다. 

- heap 메모리를 공유하기 때문에 서로 다른 스레드의 힙 메모리의 내용을 서로 읽고 쓸 수 있다.
- 독립적인 Stack을 가졌다는 것은 독립적인 함수 호출이 가능하다는 의미로 독립적인 실행 흐름으로 추가된다는 말이다.

**즉, 고유한 Stack을 가짐으로써 스레드는 독립적인 실행 흐름을 가질 수 있게 되는 것**이다.

- 스레드의 정의인 “**프로세스가 할당받은 자원을 이용하는 실행 흐름의 단위”가 이해 될것이다.**

**앞 서 말했던 예시처럼 스레드는 여러개가 있다면**  파일을 다운 받으면서 동시에 웹 서핑을 하는 등 동시 작업이 가능해진다.

참조

https://zangzangs.tistory.com/109

https://fastcampus.co.kr/media_branding_cs

https://inpa.tistory.com/entry/👩‍💻-프로세스-⚔️-쓰레드-차이#프로그램_과_프로세스

https://zangzangs.tistory.com/107
