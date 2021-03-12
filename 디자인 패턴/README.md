# 디자인패턴

참고 도서: Head First Design Patterns / 에릭 프리먼, 엘리자베스 프리먼, 케이시 시에라, 버트 베이츠 저

* ## 스트래티지 패턴

  * 알고리즘군을 정의하고 각각을 캡슐화하여 교환해서 사용할 수 있도록 만든다.

  * ```java
    abstract class Duck{
        FlyBehavior flyBehavior;
        public void setFlyBehavior(FlyBehavior fb){
            this.flyBehavior = fb;
        }
        public void performFly(){
            this.flyBehavior.fly();
        }
    }
    class RubberDuck extends Duck{
        public RubberDuck(){
            this.flyBehavior = new FlyNoWay();
        }
    }
    class MallardDuck extends Duck{
        public MallardDuck(){
            this.flyBehavior = new FlyWithWings();
        }
    }
    interface FlyBehavior{
        public void fly();
    }
    class FlyWithWings implements FlyBehavior{
        public void fly(){
            // A
        }
    }
    class FlyNoWay implements FlyBehavior{
        public void fly(){
            // B
        }
    }
    ```

  * 위 예제에서는 fly에 대한 행동을 상속하지 않고, 따로 캡슐화하여 사용한다.

    

* ## 옵저버 패턴

  * 한 객체의 상태가 바뀌면 그 객체에 의존하는 다른 객체들한테 연락이 가고 자동으로 내용이 갱신되는 방식으로 일대다 의존성을 정의
  * 주제, 옵저버 객체로 구성
  * push 방식: 주제 객체에서 옵저버 객체로 데이터를 보냄
  * pull 방식: 옵저버 객체에서 주제 객체의 데이터를 가져옴
  * pull 방식을 권장

* 

