# springstart-spring-backend

---
![image](https://user-images.githubusercontent.com/72483874/184873795-93d7b992-68f4-4a1a-9e62-4aa40c08b9d7.png)
![image](https://user-images.githubusercontent.com/72483874/184874430-e20af51a-7feb-48e0-9db8-3330ae208216.png)
![image](https://user-images.githubusercontent.com/72483874/184874083-8d4874cb-9094-436f-b6e9-d0a6cac423a7.png)
> 스프링 입문 - 스프링 부트, 웹MVC, DB 접근 기술에 대해 넓고 얕게 다룬 프로젝트입니다.
## 프로젝트 계획이유
> 스프링 프레임워크에 대한 학습을 진행하기 위해 간단한 회원 관리 웹 어플리케이션을 만들어 이해를 돕고자 했습니다.
> <br>
> 실제 동작하는 웹 애플리케이션을 다음과 같은 순서로 구현하였습니다.
> - 스프링 프로젝트 생성
> - 스프링 부트로 웹 서버 실행
> - 회원 도메인 개발
> - 웹 MVC 개발
> - DB 연동 - JDBC, JPA, 스프링데이터 JPA
> - 테스트 케이스 작성
## 프로젝트 기능 설명 

---
### [회원 관리 기능]
1. 회원 가입 <br>
    회원가입 폼에 기입된 정보를 H2 데이터베이스에 저장하는 기능
2. 회원 목록 조회 <br>
    H2 데이터베이스에 저장된 모든 회원 정보를 불러오는 기능


## 소스코드 설명

---
### [domain]
- Member
    - 회원 도메인
### [controller] <br>
- HelloController
   - 테스트 컨트롤러
   - MVC와 템플릿 엔진
   - API
- HomeController
  - 루트 페이지에 해당하는 템플릿과 매핑되는 컨트롤러
- MemberController
  - 생성자에서 MemberService객체를 주입받음
  - form 객체를 생성
  - post로 받은 폼 객체에 접근하여 얻은 정보를 바탕으로 member객체를 생성하고 저장
  - 회원 가입(get, post), 회원 목록 템플릿과 매핑
### [repository]
- MemberRepository
  - 회원 리포지토리 인터페이스
- MemoryMemberRepository
  - 데이터베이스 없이 휘발성 메모리에 저장되는 헤시테이블을 저장소로 사용
- JdbcMemberRepository
  - DataSource 객체를 주입받음
  - 순수 JDBC를 활용한 H2 DB 접근
- JdbcTemplateMemberRepository
  - JdbcTemplate를 활용한 H2 DB 접근
- JpaMemberRepository
  - JPA를 활용한 H2 DB 접근
- SpringDataJpaMemberReopsitory
  - 스프링 데이터 JPA를 활용한 H2 DB 접근
### [service]
- MemberService
  - repository 객체를 주입받음
  - 회원 등록
  - 중복 회원 검증
  - 특정 회원 조회
  - 전체 회원 조회
### [SpringConfig]
사용하고자 하는 repository를 bean으로 등록


## 정보

---
> 본 프로젝트는 inflearn에서 제공되는 **김영한의 스프링 입문 - 코드르 배우는 스프링 부트, 웹 MVC, 
> DB 접근 기술** 강의를 따라하며 이해를 돕고자 정리한 프로젝트입니다.
