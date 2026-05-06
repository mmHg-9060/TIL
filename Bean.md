## Spring Bean
IoC와 DI에서 '객체 관리'와 '주입'의 대상이 되는 객체

### Spring Bean의 정의
- 일반 객체와의 차이: new 키워드로 직접 생성한 객체가 아닌 Spring 컨테어너가 생성하고 관계 맺어주고 생명주기를 관리하는 자바 객체

## IoC, DI and Bean
- IoC: 객체의 제어권을 스프링에게 넘김 -> 스프링이 객체를 생성하고 관리함
- DI: 필요한 의존성을 외부에서 넣어줌: 스프링 컨테이너에 등록된 Bean끼리 서로 주입해줌
- Bean: IoC에 의해 관리되고 DI에 의해 조립되는 객체 그 자체

## Bean Scope
Spring은 Bean을 어떻게 생성할지 결정
- Singleton(기본): 컨테이너에 딱 하나만 생성해서 공유함
- Prototype: 요청할 때마다 새로운 객체를 생성

## Bean Lifecycle
스프링이 객체를 관리함 -> 객체가 태어나서 죽을 때 특정 작업을 시킬 수 있음
Lifecycle: 객체 생성 -> 의존 설정 -> 초기화 -> 사용 -> 소멸

## Bean 쓰는 방법
- 1. 컴포넌트 스캔: 클래스 위에 @component, @Service와 같은 어노테이션을 붙이면 Spring이 알아서 찾아냄 (자동)
- 2. 자바 설정 클래스: @Configuration 클래스 안 메서드에 @Bean을 붙여서 직접 등록 (수동)