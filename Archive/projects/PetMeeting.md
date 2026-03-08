# :pushpin: Pet Meeting  
> 반려 동물을 키우는 주인들을 위한 매칭 서비스   
> 🔗 [Github Repository](https://github.com/project-pet-meeting/repo-be-edit)   

## 1. 제작 기간 & 참여 인원
- 2022년 11월 14일 ~ 2023년 02월 12일
- 팀 프로젝트
  - [BackEnd]  : 김범석, 김하늘

</br>

## 2. 사용 기술
#### `Backend`
  - Java 11, Spring Boot 2.7, MySQL 8.0, H2
  - Spring Data JPA
  - Spring Security, JWT
  - Spring REST Docs, Spring HATEOAS
  - Junit5, Mockito
  - WebSocket, Redis

## 3. ERD 설계 

<img src="https://user-images.githubusercontent.com/110077343/224485295-b24ffd7b-bd62-484a-8b3b-007cd49b30bb.png" width="1500" height="600">

<br/> 

## 4. 핵심 기능 

이 서비스의 핵심 기능은 컨텐츠 등록 및 채팅 기능입니다.
사용자들은 애완동물 산책, 정보 공유, 카페 등 다양한 주제로 모임을 주최 할 수 있습니다.  
모임에 참여를 하면 참여한 회원들 끼리 채팅방에서 자세한 내용들에 대해 이야기를 나눌 수 있습니다. 

## 5. 사이드 프로젝트 중점 목표   

###  1) HATEOAS(Hypermedia As The Engine Of Application State)하이퍼미디어를 통해 상태 구동을 적용시켜 API 응답하기         
[바로가기](https://github.com/project-pet-meeting/repo-be-edit/blob/051741d16830e54d6ee98fbdf231b2b9c4414a53/src/main/java/sideproject/petmeeting/post/controller/PostController.java#L38-L54)  
###  2) 테스트 코드 작성         
[바로가기](https://github.com/project-pet-meeting/repo-be-edit/tree/main/src/test/java/sideproject/petmeeting)   
###  3) Spring Rest Docs 적용         
<img src="https://user-images.githubusercontent.com/110077343/224490064-df0eaebe-cae5-4905-9b77-f9e5c8fcc02f.png"></img><br/>    
[바로가기](https://github.com/project-pet-meeting/repo-be-edit/blob/main/src/docs/asciidoc/index.adoc)  
###  4) WebSocket, stomp, Redis를 이용한 채팅 기능 구현         
[바로가기](https://github.com/project-pet-meeting/repo-be-edit/issues/26)
###  5) Jenkins 빌드 및 자동 배포 적용         
<img src="https://user-images.githubusercontent.com/110077343/224490847-baa46a09-6bfd-4b55-bdeb-fc651acc7df9.png"></img><br/>   
