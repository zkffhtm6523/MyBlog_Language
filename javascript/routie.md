# routie

### - [Routie](http://projects.jga.me/routie/) 공식 사이트

### - 일반 사용법

```javascript
routie('users', function() {
    //this gets called when hash == #users
});
```

### - 응용 사용법

```javascript
routie({
    'users': function() {

    },
    'about': function() {
    }
});

// Routie 정의
routie('users/:name', function(name) {
    //name == 'bob';
});

// Routie 사용
routie('users/bob');

// Routie 사용 시 Anchor 태그로 URL 뒤에 index.jsp#bob 이렇게 붙는다

// Parameter 옵션

routie('users/?:name', function(name) {
    //name == undefined
    //then
    //name == bob
});

routie('users/');

routie('users/bob');

// wilecard

routie('users/*', function() {
});

routie('users/12312312');

// catch all:

routie('*', function() {
});

routie('anything');
```

