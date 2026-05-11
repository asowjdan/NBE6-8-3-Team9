# 🔄 나의 기여 내역 — NBE6-8-3-Team9 (가상화폐 모의투자 시스템 Kotlin 마이그레이션)

> NBE6-8-2-Team09(Java)를 Kotlin으로 마이그레이션하는 프로젝트로,
> Exchange / WebSocket / Redis 도메인 전체의 변환과 테스트 코드 작성을 담당하였습니다.

---

## 🛠 기술 스택

`Kotlin` `Spring Boot` `JPA` `Redis` `WebSocket` `GitHub Actions (CI)`

---

## 📁 담당 작업 내역

### 1. Exchange 도메인 Kotlin 마이그레이션
- `.java` → `.kt` 파일 전환 및 Kotlin 문법으로 리팩토링
- 데이터 타입 재정의 (data class, nullable 타입 적용)
- 코인 도메인의 트랜잭션 의존 방식 변경으로 인한 코드 수정
- Exchange 도메인 순환 참조 오류 해결

### 2. WebSocket / Redis 도메인 Kotlin 마이그레이션
- WebSocket 코드 통합 및 Kotlin 변환
- 코인 리스트 실제 데이터값 연결 후 Kotlin으로 전환 (`CoinListProvider` 수정)
- Redis 코드 Kotlin 변환 및 초기화 로직을 서비스 메서드로 분리
- 테스트 코드에서 Redis 초기화를 서비스의 메서드를 사용하도록 변경

### 3. 테스트 코드 작성 및 수정
- 마이그레이션된 Exchange / WebSocket / Redis 도메인 테스트 코드 작성
- 테스트 환경에 맞게 임시 SecurityConfig 수정 및 업비트 API VO 수정
- 중복 트랜잭션 및 불필요한 assertion 제거

### 4. 프론트엔드 작업 (일부)
- 프론트 프록시 재설정 및 요청 함수 재정의
- 코인 추가 시 즉각적으로 데이터가 반영되도록 로직 수정
- 프론트 코드 재구성 및 버그 수정

---

## 💡 Kotlin 마이그레이션 경험

Java로 작성된 코드를 Kotlin으로 전환하면서 두 언어의 차이를 실전에서 체감할 수 있었습니다.

- **data class 도입**: Java의 DTO/VO 클래스를 Kotlin의 `data class`로 전환하면서 `equals`, `hashCode`, `copy` 등이 자동 생성되어 코드량이 크게 줄었습니다.
- **Nullable 타입 처리**: Java에서 암묵적으로 허용되던 `null`이 Kotlin에서는 `?`로 명시되어야 해서, 기존 코드의 null 허용 여부를 코드 전반에 걸쳐 재점검하는 과정이 필요했습니다.
- **순환 참조 문제**: 도메인 간 의존 관계가 Kotlin 변환 과정에서 순환 참조 오류로 드러났고, 의존 방향을 재정리하면서 아키텍처를 더 명확하게 이해하게 됐습니다.
- **테스트 코드 적응**: Kotlin에서는 mockito 대신 mockk 사용 패턴이 자연스럽고, 테스트 DSL도 더 간결하게 작성할 수 있다는 것을 경험했습니다.

---

# 가상화폐 모의 투자 시스템
<br>




[![Back9page.png](https://i.postimg.cc/gcwLdYQB/Back9page.png)](https://postimg.cc/8sSzmV1h)


[`가상회폐 모의투자 시스템 링크`](https://d64t5u28gt0rl.cloudfront.net/)


<br>


## 개요
1. [소개](#소개)   
2. [기술스택](#기술스택)   
3. [빌드 및 사용법](#빌드-및-사용법)   
4. [문의](#문의)   


<br>


## 소개
- 데브코스 6기 8회차 9팀의 3차 프로젝트로 사용된 레포지토리 입니다.<br>


- 실제 자금 없이 안전하게 가상화폐 투자를 체험할 수 있는 모의투자 플랫폼입니다. 회원별 지갑이 자동 생성되며, 비트코인, 이더리움, 도지코인 등 주요 코인의 실시간 시세를 기반으로 거래할 수 있는 서비스를 제공합니다.


<br>


## 기술스택
### 백엔드
- [`Spring boot (with Kotlin`](https://spring.io/)
- [`JWT`]
- [`OAuth2.0`]
- [`Spring Security`]
- [`Spring Data JPA`]
- [`REST API`]
- [`Websocket`]
- [`PostgreSQL(supabase 사용)`](https://supabase.com/)


### 프론트 엔드
- [`TypeScrpt`]
- [`Next.js`](https://nextjs.org/)
- [`Tailwind CSS`](https://tailwindcss.com/)


### 배포 
- [`aws`](https://aws.amazon.com/ko/)


<br>


## 빌드 및 사용법
### 서비스 접속
- 실제 서비스는 아래 URL에서 접속 가능합니다.<br>
  [https://d64t5u28gt0rl.cloudfront.net](https://d64t5u28gt0rl.cloudfront.net)


### 로컬 빌드 및 실행 
1. 깃허브 주소를 프로젝트 폴더로 다운 받는다
<br>ex) ``
git clone project-url .``


2. 빌드 실행 <br> 
### Unix / macOS
```bash
cd project_dir/backend


# 1. Clean & Build
./gradlew clean build


# 2. Run the JAR
java -jar build/libs/your-app-name-<version>.jar
