Entity, Controller, Service, Repository, DTO는 각각 다음과 같다.
## Spring 3계층 구조
1. 사용자가 데이터를 요청하면 Controller가 먼저 받음.
2. Controller가 DTO 형태로 데이터를 받아 Service에게 일을 넘김.
3. Service는 핵심 비지니스 로직을 처리, DB 접근이 필요할 때, Repository 호출
4. Repository는 Entity를 사용해서 실제 DB에서 데이털르 꺼내오거나 저장

## Controller (컨트롤러)
클라이언트의 요청을 가장 먼저 받음.
Spring 구조에서 하는 일:
1. 사용자가 어떤 주소로 어떤 방식의 요청(GET, POST 등의 그 요청)을 보냈는지 파악
2. 요청에 담긴 데이터를 확인, 그 요청에 맞는 Service로 연결
3. Service에서 처리가 끝나면 그 결과를 다시 사용자에게 Response(응답)으로 돌려줌.

## Service (서비스)
시스템의 비지니스 로직이 실행되는 곳
Spring 구조에서 하는 일:
1. Controller가 넘겨준 데이터를 바탕으로 실제 계산, 검증, 가공의 작업을 수행
2. DB의 정보가 필요하면 Repository에 요청
3. 실제로 무엇을 하는지 여기에 작성되게 됨.

## Repository (레포지토리)
DB에 직접 접근, 데이터를 관리하는 데이터 접근 계층
Spring 구조에서 하는 일:
1. 데이터베이스에 데이터를 저장, 조회, 수정, 삭제(CRUD)
2. Spring Data JPA를 사용하면 인터페이스만 생성해도 기본적인 SQL 쿼리문을 알아서 만들어줌

## Entity (엔티티)
DB의 Table과 1:1로 매핑되는 객체
특징:
1. DB의 뼈대 그 자체 = Entity 클래스의 필드들은 실제 DB의 칼럼이 됨.
2. 핵심적인 데이터 모델, 화면이나 클라이언트에게 직접 노출되거나 수정당해서는 안 됨.

## DTO (Data Transfer Object)
각 계층 사이에서 데이터를 주고받을 때 사용하는 것
Entity 대용으로 쓰이는 이유:
Entity는 전술한 것 처럼 DB와 직결된 민감하고 중요한 객체, 사용자가 입력한 데이터를 ENtity에 바로 넣거나, Entity를 그대로 반환해버린다면, 비밀이여야 할 데이터가 노출되거나, DB 구조가 훼손될 위험이 있기 때문에, 요청과 응답을 위한 것인 DTO를 만들어서 필요한 데이터만 담아서 전달함.