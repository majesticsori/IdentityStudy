Asp.net core identity 

- 로그인, 로그아웃, 개별 인증(관리자, 일반 사용자)
- 일반 사용자 (나이가 19세이상)

# Identity 테이블 구조 
1. dbo.AspNetUsers => ApplicationUser (User Class)
- Id, 비밀번호, 사용자 이름 ... 

2. dbo.AspNetRoles => ApplicatoinRole (Role Class)
- 이 웹사이트에 회원 분류 
- 슈퍼 관리자, 관리자, 일반사용자 

3. dbo.AspNetUserRoles => 
- 사용자 권한 매핑 테이블 

4. dbo.AspNetUserClaims => 5명의 사용자 -> 일반 사용자(role)
- 2명이 나이 20세 미만 -> 20세 미만은 특정 게시판 진입금지 
- 나이에 따라 권한 정의 [HttpGet, Authorize(Claims ... Age > 20)]

5. dbo.AspNetRoleClaims > 
- 관리자 > 1등, 2등, 3등

6. dbo.AspNetUserLogins 
- 외부 로그인 Oauth1.0/2.0

7. dbo.AspNetUserTokens
- 외부 로그인 Tokens 인증 방식 