# T1 Community Board Project
> **"For the Unstoppable Era"** > Java Spring Boot와 JDBC를 활용한 T1 컨셉의 커뮤니티 게시판입니다.

---

## Project Preview
* **Concept:** T1 Esports 팀의 아이덴티티(Black, Red, Gold)를 반영한 UI/UX
* **Theme:** 다크 모드 기반의 몰입감 있는 게시판 인터페이스

---

## 주요 구현 기능 (Key Features)

### 1. 게시판 CRUD (Core Logic)
- **Create:** Spring Form 태그와 유효성 검사를 통한 게시글 작성
- **Read:** `JdbcTemplate`과 `RowMapper`를 이용한 안정적인 데이터 렌더링
- **Update/Delete:** 게시글 수정 및 삭제 관리

### 2. 전략적 검색 시스템 (Search System)
- **Dynamic SQL:** 사용자가 선택한 검색 조건(제목, 작성자, 내용)에 따라 동적으로 SQL 쿼리를 생성하여 필터링
- **Keyword Matching:** `LIKE` 연산자와 와일드카드(`%`)를 조합한 유연한 키워드 검색 기능 구현

---

## Tech Stack
| Category | Tech Stack |
| :--- | :--- |
| **Backend** | Java 17, Spring Boot 5.0, Spring JDBC |
| **Database** | Oracle Database (XE 21c) |
| **Frontend** | JSP (Custom Dark Theme) |
| **Build Tool** | Maven |

---

## Project Architecture
```text
com.example.board
├── controller  # 게시판 비즈니스 로직 매핑 (BoardController)
├── service     # 트랜잭션 및 게시판 서비스 레이어
├── dao         # Oracle DB 연동 및 CRUD 쿼리 수행 (BoardDAO)
└── domain      # 게시글 데이터 구조 정의 (Board DTO)

src/main/webapp/WEB-INF/views/board
├── list.jsp        # T1 컨셉의 다크 테마 게시판 목록 및 검색 바
├── insertForm.jsp  # 신규 미션(게시글) 등록 폼
└── detail.jsp      # 게시글 상세 조회 및 수정/삭제 인터페이스
