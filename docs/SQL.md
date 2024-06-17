![image](https://github.com/mannazo/mannazo/assets/34194400/6fb17fc8-20e4-418c-8620-0192857e07c4)


```
-- User table
CREATE TABLE User (
    user_id UUID NOT NULL, -- 사용자 고유 식별자
    email VARCHAR(255) NOT NULL, -- 사용자 이메일
    password VARCHAR(255) NOT NULL, -- 사용자 비밀번호
    name VARCHAR(255) NOT NULL, -- 사용자 이름
    nationality INT NULL, -- 사용자 국적 (선택 사항)
    language VARCHAR(255) NULL, -- 사용자 언어 (선택 사항)
    profile_photo VARCHAR(255) NULL, -- 프로필 사진 URL (선택 사항)
    bio TEXT NULL, -- 자기소개 (선택 사항)
    residence VARCHAR(255) NULL, -- 사용자 거주지 (선택 사항)
    role ENUM('Admin', 'User') NULL, -- 사용자 권한
    last_login_time TIMESTAMP NULL, -- 마지막 로그인 시간
    PRIMARY KEY (user_id) -- 기본 키 설정
);
```
```
-- Travel Plan table
CREATE TABLE TravelPlan (
    travel_id UUID NOT NULL, -- 여행 계획 고유 식별자
    user_id CHAR(36) NOT NULL, -- 사용자 식별자 (외래 키)
    destination VARCHAR(255) NOT NULL, -- 여행 목적지
    start_date DATE NOT NULL, -- 여행 시작 날짜
    end_date DATE NOT NULL, -- 여행 종료 날짜
    interests TEXT NULL, -- 여행 관심사 (선택 사항)
    status ENUM('Registered', 'Matching', 'Matched', 'Completed') NOT NULL, -- 여행 상태
    PRIMARY KEY (travel_id) -- 기본 키 설정
);
```
```
-- Application table
CREATE TABLE Application (
    application_id CHAR(36) NOT NULL, -- 신청 고유 식별자
    status ENUM('Applied', 'Accepted', 'Rejected') NOT NULL, -- 신청 상태
    user_id UUID NOT NULL, -- 사용자 식별자 (외래 키)
    related_id CHAR(36) NOT NULL, -- 다른 관련 식별자 (예: 여행 계획 식별자)
    PRIMARY KEY (application_id) -- 기본 키 설정
);
```


```
-- Chat table
CREATE TABLE Chat (
    chat_id CHAR(36) NOT NULL, -- 채팅 고유 식별자
    user_id CHAR(36) NOT NULL, -- 사용자 식별자 (외래 키)
    message TEXT NOT NULL, -- 채팅 메시지 내용
    timestamp TIMESTAMP NOT NULL, -- 메시지 타임스탬프
    PRIMARY KEY (chat_id) -- 기본 키 설정
);
```
```
-- Review table
CREATE TABLE Review (
    review_id CHAR(36) NOT NULL, -- 리뷰 고유 식별자
    trip_id CHAR(36) NOT NULL, -- 여행 계획 식별자 (외래 키)
    reviewer_id CHAR(36) NOT NULL, -- 리뷰 작성자 식별자 (외래 키)
    reviewee_id CHAR(36) NOT NULL, -- 리뷰 대상자 식별자 (외래 키)
    rating INT NOT NULL, -- 평점
    content TEXT NOT NULL, -- 리뷰 내용
    timestamp TIMESTAMP NOT NULL, -- 리뷰 타임스탬프
    PRIMARY KEY (review_id) -- 기본 키 설정
);
```
```
-- Inquiry table
CREATE TABLE Inquiry (
    inquiry_id CHAR(36) NOT NULL, -- 문의 고유 식별자
    user_id CHAR(36) NOT NULL, -- 사용자 식별자 (외래 키)
    title VARCHAR(255) NOT NULL, -- 문의 제목
    content TEXT NOT NULL, -- 문의 내용
    status ENUM('Received', 'Processing', 'Completed') NOT NULL, -- 문의 상태
    timestamp TIMESTAMP NOT NULL, -- 문의 타임스탬프
    PRIMARY KEY (inquiry_id) -- 기본 키 설정
);
```
```
-- Primary Key Constraints
ALTER TABLE User ADD CONSTRAINT PK_user PRIMARY KEY (user_id);
ALTER TABLE TravelPlan ADD CONSTRAINT PK_travel_plan PRIMARY KEY (travel_id);
ALTER TABLE Application ADD CONSTRAINT PK_application PRIMARY KEY (application_id);
ALTER TABLE Chat ADD CONSTRAINT PK_chat PRIMARY KEY (chat_id);
ALTER TABLE Review ADD CONSTRAINT PK_review PRIMARY KEY (review_id);
ALTER TABLE Inquiry ADD CONSTRAINT PK_inquiry PRIMARY KEY (inquiry_id);
```
