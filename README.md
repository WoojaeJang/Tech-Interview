# Tech-Interview
빅데이터 엔지니어로 취업을 준비하며 기술 면접을 위한 CS 지식 정리

## 목차
- [1. 스택과 큐](#1-스택과-큐)
- [2. Deque](#2-deque)
- [3. 자료형 종류](#3-자료형-종류)
- [4. 함수의 종류](#4-함수의-종류)
- [5. 메소드와 함수](#5-메소드와-함수)
- [SpringBoot request 처리 과정]()
- [디자인 패턴]()
- [MVC]()
- [API]()
- [SQL JOIN]()
- [SQL 서브쿼리]()

<br/>

## 1. 스택과 큐

#### 스택(Stack)
- 영어로 Stack '쌓다' 라는 의미
- 프로그래밍에서 목록 혹은 리스트에서 접근이 한쪽에서만 가능한 구조
- LIFO(Last-In, First-Out)가 기본원리
    ![01_Stack](./README_images/01_Stack.jpg)
- 대표적인 내장함수
	- push
	- peek
	- pop

<br/>

#### 큐(Queue)
- 영어로 Queue '일이 처리되기를 기다리는 리스트' 라는 의미
- 프로그래밍에서 목록 혹은 리스트에서 접근이 양쪽에서 가능한 구조
- FIFO(First-In, First-Out)가 기본원리
    ![02_Queue](./README_images/02_Queue.jpg)
- 대표적인 내장함수
	- put
	- peek
	- get

<br/>


## 2. Deque
- deque는 stack과 queue의 기능을 모두 가진 객체
- 양방향 queue
- 앞, 뒤 양쪽 방향에서 요소를 추가 제거할 수 있다.
- 대표적인 내장 함수
    - deque.append(item): item을 데크의 오른쪽 끝에 삽입한다.
    - deque.appendleft(item): item을 데크의 왼쪽 끝에 삽입한다.
    - deque.pop(): 데크의 오른쪽 끝 엘리먼트를 가져오는 동시에 데크에서 삭제한다.
    - deque.popleft(): 데크의 왼쪽 끝 엘리먼트를 가져오는 동시에 데크에서 삭제한다.
    - deque.extend(array): 주어진 배열(array)을 순환하면서 데크의 오른쪽에 추가한다.
    - deque.extendleft(array): 주어진 배열(array)을 순환하면서 데크의 왼쪽에 추가한다.
    - deque.remove(item): item을 데크에서 찾아 삭제한다.
    - deque.rotate(num): 데크를 num만큼 회전한다(양수면 오른쪽, 음수면 왼쪽).

<br/>


## 3. 자료형 종류

#### 기본 자료형
- 숫자형
    - int (정수형)
    - float (실수형)
    - complex (복소수형)
- 논리형
    - bool (True / False)

<br/>

#### 군집 자료형
- 시퀀스(Sequence) 형태 : 순서가 중요
    - str (문자열) : 문자열을 위한 list와 같은 객체 자료형 (순서O, 중복O, 수정X)
    - list (리스트) : 순서가 있는 값의 나열 (순서O, 중복O, 수정O)
    - tuple (튜플) : list와 유사, 읽기 전용 (순서O, 중복O, 수정X)
- 비 시퀀스(Non Sequence) 형태 : 순서가 중요하지 않음
    - set (집합) : 순서가 없고, 중복을 허용하지 않는 값들의 모임 (순서X, 중복X, 수정O)
    - dict (사전) : 순서가 없고, 반드시 키를 사용하여 원소에 접근 (순서X, 중복X, 수정O)

<br/>

#### 군집 자료형 비교
||List|Tuple|Set|Dictionary|
|---|---|---|---|---|
|순서 유무|O|O|X|X|
|중복 허용|O|O|X|X|
|수정 가능|O|X|O|O|
|예시|[1, 2, 3]|(1, 2, 3)|{1, 2, 3}|{'a' : 1, 'b' : 2, 'c' : 3}|
|주요 특징|index를 지정하여 값 변경 가능|수정이 불가능하지만 속도가 빠름|List의 중복값 삭제용으로 주로 사용|Key와 Value로 구성|

<br/>

## 4. 함수의 종류

#### 내장함수
- 파이썬 인터프리터에서 기본적으로 포함하고 있는 함수
- import를 필요로 하지 않음
- 내장함수 목록
    - abs(), all(), any(), ascii()
    - bin(), bool(), breakpoint(), bytearray(), bytes()
    - callable(), chr(), classmethod(), compile(), complex()
    - delattr(), dict(), dir(), divmod()
    - enumerate(), eval(), exec()
    - filter(), float(), format(), frozenset()
    - getattr(), globals(), hasattr(), hash(), help(), hex()
    - id(), input(), int(), isinstance(), issubclass(), iter()
    - len(), list(), locals()
    - memoryview(), min(), map(), max(), next()
    - object(), oct(), open(), ord()
    - pow(), print(), property()
    - range(), repr(), reversed(), round()
    - set(), setattr(), slice(), sorted(), staticmethod(), str(), sum(), super()
    - tuple(), type()
    - vars()
    - zip()
    - __import__()

<br/>

#### 외장함수
- import 문을 사용하여 외부의 라이브러리에서 제공하는 함수
- 파이썬 기본 라이브러리들은 파이썬 설치 시 자동으로 설치
- 기본 라이브러리 목록
    - Sys : 파이썬 인터프리터가 제공하는 변수들과 함수들을 직접 제어할 수 있게 해주는 모듈.
    - Pickle : 객체의 형태를 그대로 유지하면서 파일에 저장하고 불러올 수 있게 하는 모듈.
    - Os : 환경 변수나 디렉터리, 파일 등의 OS 자원을 제어할 수 있게 해주는 모듈.
    - Shutil : 파일을 복사해 주는 파이썬 모듈.
    - Glob: 특정 디렉터리에 있는 파일 이름 모두를 알아야 할 때 사용하는 모듈. 디렉터리 내의 파일들을 읽어서 리스트로 리턴.
    - Tempfile: 파일을 임시로 만들어서 사용할 때 유용한 모듈.
    - Time: 시간과 관련 모듈.
    - Calendar: 파이썬에서 달력을 볼 수 있게 해주는 모듈.
    - Random: 난수(규칙이 없는 임의의 수)를 발생시키는 모듈.
    - Webbrowser: 자신의 시스템에서 사용하는 기본 웹 브라우저가 자동으로 실행되게 하는 모듈.

<br/>

#### 사용자 정의함수
- def 문을 사용해서 사용자가 직접 정의하는 함수


<br/>

## 5. 메소드와 함수


## SpringBoot request 처리 과정


## 디자인 패턴


## MVC 패턴


## API


## SQL JOIN


## SQL 서브쿼리



# 참조 사이트
- https://leonkong.cc/posts/python-deque.html
- http://www.ktword.co.kr/test/view/view.php?m_temp1=5926
- https://artist-developer.tistory.com/22
- https://daco2020.tistory.com/60
- https://cording-artist.tistory.com/124
- https://sdc-james.gitbook.io/onebook/3./3.6./3.6.1.


<br/>

# 사진 출처
- [1. 스택과 큐] : 
    - https://seill.tistory.com/576