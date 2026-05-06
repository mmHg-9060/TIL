## Spring Security
Spring Security는 애플리케이션의 인증(Authentication)과 인가(Authorization)을 처리하는 프레임워크
아키텍처: Filter Chain
Spring Security는 수많은 Filter들이 사슬처럼 엮여서 동작하는데, 요청이 들어오면 이 필터들을 하나씩 거치면서 검문을 하게 됨
- SecurityContextHolder: 인증된 사용자의 정보를 담는 저장소
- AuthenticationManager: 실제 인증을 처리하는 관리자
- UserDetailsService: DB에서 사용자 정보를 가져오는 인터페이스

## JWT
JWT는 정보를 안전하게 전송하기 위해 상태가 없는(Stateless) 토큰 인증 방식
### JWT의 구조
- 1. Header: 토큰의 타입, 암호화 알고리즘
- 2. Payload: 담고 싶은 데이터
- 3. Signature: 서버만 알고 있는 키로 생성한 암호화 서명