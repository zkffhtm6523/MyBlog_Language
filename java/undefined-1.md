# 인터페이스

## 1. Comparable 인터페이스

> 클래스가 자신이 갖고 있는 객체를 정렬할 수 있으려면, Comparable 인터페이스를 구현해야 한다.

  
Comparable 인터페이스는 문자열 대 문자열, 직원 대 직원 등으로 비교해야한다. 따라서 Comparable 인터페이스는 \*\*타입 파라미터\*\*를 받는다.  
\`\`\`java public interface Comparable{ int compareTo\(T other\); } \`\`\` 예를 들어 String 클래스는 Comparable을 구현한다. 그러므로 String의 compareTo 메서드는 서명이 다음과 같다.

```java
int compareTo(String other)

// x.compareTo(y)를 호출하면 compareTo 메서드는 정수 값을 반환한다. 이 정수 값은 x와 y 중  
// 어느 것이 먼저 와야 하는지를 나타낸다.

// 양수 값 반환 : x가 y 다음에 온다
// 음수 값 반환 : y가 x 다음에 온다
```

  
\`\`\`java public class Employee implements Comparable{ // 정수형 비교 public int compareTo\(Employee other\){ return getId\(\) - other.getId\(\); // ID가 항상 0 이상이면 사용할 수 있다. }

```java
...

// 부동소수점 비교
public int compareTo(Employee other){
    return Double.compare(salary, other.salary);
}
```

}

```java

<br>
# 2. Comparator 인터페이스

> 문자열의 길이 비교는 Comparable로 비교할 수 없다.

<br>

```java
public interface Comparator<T>{
    int compare(T first, T second);
}


class LengthComparator implements Comparator<String>{
    public int compare(String first, String second){
        return first.length() - second.length();
    }
}

Comparator<String> comp = new LengthComparator();
if(comp.compare(words[i], words[j]) > 0)...


String[] friends = {"Peter", "Paul", "Mary"};
Arrays.sort(friends, new LengthComparator());
```

