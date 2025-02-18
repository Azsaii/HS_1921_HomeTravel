# 방구석 국내여행 사이트
이 프로젝트는 방구석에서 간접적으로 국내여행을 경험하기 위해 제작된 웹 애플리케이션입니다.   
백엔드는 Spring Boot를 사용하고 프론트엔드는 React로 개발되었습니다.  

## 기능
### Main
- **검색어를 이용한 지도 및 날씨, 뉴스 정보 조회**
  - 메인 화면에서 검색어를 입력하면 지도가 표시되고, 입력한 위치의 날씨 및 뉴스 정보가 우측에 표시됩니다.    
  - 이 정보는 카카오맵 API, 기상청 날씨 API와 네이버 뉴스 API를 이용하여 가져옵니다.  
- **관광지 정보 조회**
  - 관광 버튼을 클릭하면 검색어와 관련된 이미지를 투어 API를 이용하여 가져와서 표시합니다.  
  - 세부 분류로 문화시설, 숙박, 쇼핑 등을 필터링할 수 있습니다.  
- **검색어 관련 유튜브 동영상 표시**
  - 이 기능은 유튜브 API를 활용하여 구현되었습니다.    
  - 유튜브 버튼을 클릭하면 우측 사이드바가 열리고 검색어와 관련된 유튜브 동영상이 나타납니다.  
  - 스크롤 하단으로 끝까지 내리면 추가 버튼을 클릭해서 다음 관련 영상들을 불러올 수 있습니다.  
  - 유튜브 영상 위에 마우스를 올리면 하단에 사각형 확장 버튼이 나타나고, 클릭하면 모달이 나타나서 크게 볼 수 있습니다.  
   - 모달에서 좌우로 영상을 넘겨 볼 수 있습니다.
- **검색어 관련 마커 리스트 표시**
  - 검색어 입력하면 관련된 마커가 지도에 표시되고, 좌측에 마커 리스트가 표시됩니다.  
- **로드 뷰**
  - 관광 아이콘 우측의 파란색 로드 뷰 아이콘을 클릭하면 좌우로 크기조절이 가능한 로드 뷰가 나타납니다.  
  - 지도에서 로드 뷰를 보고싶은 지점을 클릭하면 로드 뷰 마커가 찍히고 해당 지점 주변의 로드 뷰가 보입니다.
  - 로드 뷰 마커는 잡고 드래그해서 움직일 수 있습니다.  
  - 로드 뷰 아이콘을 눌렀을 때 지도에 보이는 파란 선은 로드 뷰를 볼 수 있는 도로입니다.  
  - 파란 선 이외의 장소에 마커를 찍으면 가까운 도로의 로드 뷰가 보입니다.
  - ※ 도로와 너무 먼 장소에 마커를 찍으면 로드뷰를 볼 수 없습니다!
- **chat GPT를 이용한 여행 계획 생성**
  - 유튜브 버튼 하단의 GPT 버튼을 누르고 목적지와 여행 일 수를 입력하면 chat GPT가 사용자에게 여행 계획을 생성하여 제안해줍니다.
- **카카오 로그인 기능**
  - 카카오계정으로 로그인 할 수 있습니다.
- **로그인/회원가입 기능**
  - 아이디, 비밀번호, 이메일, 사용자 이름으로 회원가입을 할 수 있으며, 아이디, 비밀번호를 입력하여 로그인 할 수 있습니다.
### Planner
- **여행지를 카드 단위 관리**<br>
  - 플래너 화면에서 여행 일정을 react-beautiful-dnd 라이브러리를 이용해 카드 단위로 드래그 앤 드롭이 가능하게 구현했습니다.
- **여행지 추가 및 정보 확인**<br>
  - 카카오맵 API를 이용해서 여행지를 카드로 추가 할 수 있습니다. 카드를 누르면 모달창이 나오고 여행지 정보를 확인할 수 있습니다.
- **여행 동선 및 시간확인**<br>
  - 계획한 여행지들이 추가되있는 컬럼을 누르면 해당 일자의 동선 및 이동거리, 예상 이동 시간 등을 보여줍니다. 
### SNS
  SNS 화면에서는 사용자가 여행에 관한 게시물을 작성하고 공유할 수 있습니다.
- **게시물 조회**<br>
  - 게시물을 누르면 모달창이 띄워지고 사진, 메모, 댓글, 카카오맵 API를 이용한 위치정보를 자세히 조회할 수 있습니다.
  - react-slick 라이브러리를 사용하여, 사용자가 화살표를 클릭하면 게시물의 다양한 이미지를 슬라이더 형식으로 볼 수 있도록 구현했습니다.
- **게시물 작성**<br>
  - 게시물에는 사진, 메모, 카카오맵 API를 이용한 위치 정보를 넣어서 작성할 수 있습니다.
- **게시물 수정/삭제**<br>
  - 자신이 작성한 게시물은 언제든지 수정 및 삭제할 수 있습니다.
- **댓글 기능**<br>
  - 다른 사용자의 게시물에 댓글을 작성할 수 있습니다.

## 사용 API
- **지도 데이터(검색, 마커, 로드 뷰)**: 카카오맵 API
- **날씨 정보**: 기상청 날씨 API
- **뉴스 정보**: 네이버 뉴스 검색 API
- **유튜브 검색**: YouTube Data API v3
- **GPT 서비스**: OpenAI GPT (ChatGPT)
- **관광지 이미지 검색**: 한국관광공사 Tour API
- **지도 경로 계산**: 카카오 모빌리티 API

## 백엔드 개발 환경 설정
1. **IntelliJ 설정**<br>
   - IntelliJ를 열고 프로젝트를 로드합니다.
   - File > Project Structure> Project Settings> Project 로 이동합니다.
   - SDK를 OpenJDK 21을 선택합니다.
    
2. **Gradle 설정**<br>
   - File > Settings > Build, Execution, Deployment > Build Tools > Gradle로 이동합니다.
   - Gradle JVM에서 OpenJDK 21을 선택합니다.

3. **application.properties 설정**<br>
   - `src/main/resources/application.properties` 파일을 엽니다.
   - `file.dir` 속성을 SNS 이미지가 저장될 폴더 경로로 설정합니다.
   
   예시
   > file.dir= C:/Users/cksgu/Desktop/demo/demo/file/
   
   경로의 맨 끝에 '/' (슬래시)를 꼭 추가해주세요!
## 실행방법 <br>
1. IntelliJ에서 HomeTravel_Back 폴더를 open 한다.
2. 위에 백앤드 개발 환경 설정이 맞는지 확인한다.
3. src>main>java>com.example.demo>service 폴더의 DemoApplication을 실행 시킨다.
4. visual studio code에서 HomeTravel_Front 폴더를 open한다.
5. npm install 후 npm start를 입력해서 실행시킨다.

## 메인화면 스크린샷 <br>
![결과사진1 메인화면](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/aedae6ea-6261-46ef-8c0b-fdd9f8595eae)
![결과사진6 마커리스트](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/bbdf49fd-0549-450e-9979-3170c90dcffd)
![결과사진2 유튜브리스트](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/89c975ae-832f-4ab6-9b34-64c8f1378623)
![결과사진7 유튜브추가버튼](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/be74b8c8-880c-40ce-9443-f34df6d4c8d5)
![결과사진3 유튜브확대](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/e2af35fc-8600-434e-b10b-7c9dc159485f)
![결과사진4 gpt](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/601df140-e9a6-4cdb-b990-3632359950e4)
![결과사진5 로드뷰](https://github.com/Azsaii/HomeTravel_Front/assets/120641012/dc24af06-e9b7-463f-ac28-819f5adbfb23)


