# LunaLobby Lite

## 프로젝트 개요
- 목적: 캐릭터 채팅 서비스의 로비/마이페이지/제작 화면 흐름을 빠르게 검증하는 프로토타입
- 형태: 단일 페이지 UI 데모 (탭/메뉴 기반)
- 백엔드 연동: 아직 없음 (로컬 데모 상태)

## 주요 기능

### 1) 홈 로비
- 빠른 시작(신작/랭킹/내 채팅)
- 공지 미리보기, 실시간 인기 태그
- 신작 추천
- 캐릭터 검색 + 정렬(인기순/최신순/좋아요순)
- 즐겨찾기 토글

### 2) 기본 탭
- 공지사항
- 자유게시판
- 회원가입/로그인 화면(데모)
- 공식/신작/랭킹/팔로잉/상위권/좋아요 작품

### 3) 내 채팅 (로컬 데모)
- 간단한 키워드 기반 응답
- 대화 로그 로컬 저장/초기화
- API 미연동 상태

### 4) 성인인증 ON/OFF (기초)
- ON/OFF 상태 전환
- 상태 로컬 저장

### 5) 마이페이지/계정 관리 (기초)
- 내정보, 포인트/패키지, 구독/차단/인센티브
- 회원정보 수정, 비밀번호 변경
- 정산 신청, 빠른 메뉴 설정

### 6) 제작자/캐릭터 제작 (Lite)
- 캐릭터 기본정보/세계관/프롬프트/규칙 입력
- 로어북 항목 추가 (최대 100개 권장)
- 이미지 업로드 후 512px 이하 리사이즈 + JPG 압축
- 임시저장/생성 데이터 localStorage 저장

## 기술 스택
- **Backend**: Spring Boot 4.0.3 (Web MVC, Thymeleaf 의존성 포함)
- **Language**: Java 17
- **Frontend**: HTML/CSS/Vanilla JavaScript (정적 파일)
- **Build**: Gradle
- **Storage (Demo)**: Browser localStorage

## 실행 방법

### 1) 요구사항
- JDK 17+
- Gradle Wrapper 사용 가능 환경

### 2) 실행
```bash
cd /home/ubuntu/projects/homepage
./gradlew bootRun
```

### 3) 접속
- `http://localhost:8080/`

## 현재 구조
```text
src/main/resources/
├─ application.properties
└─ static/
   └─ index.html   # 메인 데모 UI
```

## 저장 키(localStorage)
- `lunalobby-create-draft-v1` : 캐릭터 제작 임시저장
- `lunalobby-lite-fav-v1` : 로비 즐겨찾기
- `lunalobby-local-chat-v1` : 채팅 로그
- `lunalobby-adult-toggle-v1` : 성인인증 상태
- `lunalobby-creator-home-v1` : 제작자 홈페이지 기초 데이터

## 제한사항
- 실제 회원 인증/권한 처리 없음
- 서버 DB 연동 없음
- 결제/정산/구독은 UI 데모 단계
- 채팅 응답은 규칙 기반 데모

## 다음 단계(권장)
1. REST API 설계 및 연동
2. DB 스키마 설계 (회원/캐릭터/채팅/좋아요/구독)
3. 인증/인가(JWT 등) 적용
4. 파일 업로드 저장소(S3 등) 연동
5. 테스트 코드 및 배포 파이프라인 정리
