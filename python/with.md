# with

### 개념

> 자원을 획득하고 사용 후 반납해야 하는 경우 주로 사용합니다.

> 1. 자원을 획득한다
> 2. 자원을 사용한다
> 3. 자원을 반납한다

### 문법

```python
with EXPRESSION [as VARIABLE]:
	BLOCK
```

### 예제

```python
class Hello:

    def __enter__(self):
        # 사용할 자원을 가져오거나 만든다(핸들러 등)
        print('enter...')
        return self # 반환값이 있어야 VARIABLE를 블록내에서 사용할 수 있다
        
    def sayHello(self, name):
        # 자원을 사용한다. ex) 인사한다
        print('hello ' + name)

    def __exit__(self, exc_type, exc_val, exc_tb):
        # 마지막 처리를 한다(자원반납 등)
        print('exit...')
        
with Hello() as h:
    h.sayHello('obama')
    h.sayHello('trump')

# 결과
enter...
hello obama
hello trump
exit...
```

### 해석

> 클래스의 객체를 바로 만들고 만든 객체를 이용하여 인사를 하고 만든 객체를 소멸시킵니다.

> 객체의 라이프사이클 **\(생성 &gt;&gt; 사용 &gt;&gt; 소멸\)** 을 설계할 수 있습니다.

