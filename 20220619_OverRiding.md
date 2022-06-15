# 오버라이딩 (OverRiding)
  - 오버라이딩이란?
    조상 클래스로부터 상속받은 메서드의 내용을 변경하는 것을 오버라이딩이라고 한다. 
    상속받은 메서드를 그대로 사용하기도 하지만, 자손 클래스 자신에 맞게 변경해야하는 경우가 많은데, 이럴 때 조상의 메서드를 오버라이딩 한다.
    
```
class Point {
  int x;
  int y;
  
  String getLocation() {
    return "x : " + x + ", y : " + y;
  }
}

class Point3D extends Point {
  int z;
  
  String getLocation() {    // 오버라이딩
    return "x : " + x + ", y : " + y + ", + z : " + z;
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


# 오버로딩 ( OverLoading)
  - 오버로딩이란?
    기존에 없는 새로운 메서드를 정의하는 것
    클래스에 메서드를 정의할 때 같은 이름이지만 서로 다른 매개변수의 형식을 가지고 있는, 메서드를 여러개를 정의할 수 있는 방법
 
 ```

c1.setOprands(10, 20, 30);

public void setOprands(int left, int right, int third) {
  this.left = left;
  this.right = right;
  this.third = third;
}
```
// 두 개의 매개변수를 받기위해서는 두 개의 매개변수를 받는 이름이 다른 메서드를 선언해서 사용해야 한다.

```
    c1.setOprands(10, 20);
    //...
    //...
```    
    
// 오버로딩을 사용하면 매개변수의 타입이나 갯수가 다른 같은 이름의 메서드를 사용할 수 있다 (더 깔끔한 코딩으로 바뀜)

```
package org.opentutorials.javatutorials.overloading.example;

calss Calcultor {
  it left, right;
  int third = 0;
  
  public void setOprands(int left, int right) {
    System.out.println("setOprands(int left, int right)");
    this.left = left;
    this.right = right;
  }
  
  public void setOprands(int left, int right, int third) {
    this.setOprands(left, right);            
    
    System.out.println("setOprands(int left, int right, int third)");
    this.third = third;
  }

  public void sum() {
    System.out.println(this.left + this.right + this.third);
  }
  
  public void avg() {
    System.out.println((this.left + this.right + this.third)/2);
  }
 
}

public class CalculatorDemo {
  public static void main (String [] args) {
    Calculator c1 = new Calculator();
    c1.setOprands(10, 20);
    c1.sum();
    c1.avg();
    c1.setOprands(10, 20, 30);
    c1.sum();
    c1.avg();
  }
  
}

```

// 오버로딩을 사용하지 않는다면 사용자는 필요한 매개변수의 메서드명을 기억하고 이를 맞게 사용해야 하는 수고로움이 있다.




