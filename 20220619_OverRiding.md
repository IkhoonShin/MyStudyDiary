

# 오버로딩 ( OverLoading)
  - 오버로딩이란?
    기존에 없는 새로운 메서드를 정의하는 것
    클래스에 메서드를 정의할 때 같은 이름이지만 서로 다른 매개변수의 형식을 가지고 있는, 메서드를 여러개를 정의할 수 있는 방법
 
 ```

public class Calculation1 {
  public void add1 (int i, int j) {
    System.out.println(i + j);
  }
}

public class Calculation2 {
  public void add2 (int i, int j, int k) {
    System.out.println(i + j + k);
  }
}

public class Calculation3 {
  public void add3 (double i, double j) {
    System.out.println(i + j);
  }
}
  
class Overloading1 {

  public static void main (String [] args) {
    
    Calculation1 obj = new Calculation1();
    obj.add1(10, 20);
    
    Calculation2 obj = new Calculation2();
    obj.add2(10, 20, 30);
    
    Calculation3 obj = new Calculation3();
    obj.add3(3.4, 5.6);
    
  }

}

```
// 두 개의 매개변수를 받기위해서는 두 개의 매개변수를 받는 이름이 다른 메서드를 선언해서 사용해야 한다    
// 오버로딩을 사용하면 매개변수의 타입이나 갯수가 다른 같은 이름의 메서드를 사용할 수 있다 (더 깔끔한 코딩으로 바뀜)

```

public class Calculation {
  public void add (int i, int j) {
    System.out.println(i + j);
  }
  
  public void add (int i, int j, int k) {
    System.out.println(i + j + k);
  }
  
  public void add (double i, double j) {
    System.out.println(i + j);
  }

}


class Overloading1 {

  public static void main (String [] args) {
    Calculation obj = new Calculation();
    
    obj.add(10, 20);
    obj.add(10, 20, 30);
    obj.add(3.4, 5.6);
    
  }

}

```

// 오버로딩을 사용하지 않는다면 사용자는 필요한 매개변수의 메서드명을 기억하고 이를 맞게 사용해야 하는 수고로움이 있다.
// 오버로딩된 메서드 가운데 어떤 메서드를 호출할 것인지는 컴파일 시점에 결정이 된다.


-------------------------------------------------------------------------------------------------------------------------------------


# 오버라이딩 (OverRiding)
  To ignore or refuse to accept a suggestion, idea, or method that already exists or operates

  - 오버라이딩이란?
    조상 클래스로부터 상속받은 메서드의 내용을 변경하는 것을 오버라이딩이라고 한다. 
    상속받은 메서드를 그대로 사용하기도 하지만, 자손 클래스 자신에 맞게 변경해야하는 경우가 많은데, 이럴 때 조상의 메서드를 오버라이딩 한다.
    
```
class Member {
  public void age() {
    System.out.println("나이는 몇살입니다.");
  }
}

class Noohki extends Member {
  public void age() {
    System.out.println("나이는 31살입니다.");
  }
}

class Jay extends Member {
  public void age() {
    System.out.println("나이는 26살입니다.");
  }
}

class Bogus extends Member {
  public void age() {
    System.out.println("나이는 30살입니다.");
  }
}

class Belllake extends Member {
  public void age() {
    System.out.println("나이는 29살입니다.");
  }
}

```

```

class Overriding {

  publicl static void main(String [] args) {
    Member member = new Member();
    
    Noohki noohki = new Noohki();
    Jay jay = new Jay();
    Bogus bogus = new Bogus();
    Belllake belllake = new Belllake();
    
    noohki.age();
    jay.age();
    bogus.age();
    belllake.age();
    
  }

}


```

## 오버라이딩의 조건
  1. 조상클래스의 메서드와 이름이 같아야 한다.
  2. 조상클래스의 메서드와 매개변수가 같아야 한다.
  3. 조상클래스의 메서드와 반환타입이 같아야 한다.
  
  -한마디로 요약하면 선언부가 서로 일치해야 한다는 것이다. 다만, 접근 제어자와 예외는 제한된 조건 하에서만 다르게 변경할 수 있다.
  
  **예외조건
  
    1. 접근 제어자는 조상 클래스의 메서드보다 좁은 범위로 변경 할 수 없다.
      ex) 접근제어자의 접근범위 ( public > protected > (default) > private )
    2. 조상클래스의 메서드보다 많은 수의 예외를 선언할 수 없다.
      ex) 단순히 갯수 뿐만이 아니라 예외의 상대 크기도 고려해야 한다.

// 오버라이딩은 동적으로 선택되기 때기문에, 자식클래스에서 재정의한 메서드가 실행시간에 호출이 됨







