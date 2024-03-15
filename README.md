# GlobalAIBootCamp2024

## 서문
안녕하세요?  
이번 글로벌 에이아이 부트캠프 2024 서울 행사에서 '코파일럿(Copilot)'을 맛보기로 했습니다.  
자산관리, 출석, 트래킹, 정보전달 등에 유용한 QR 코드를 앱에서 확인하는 방법에 대해서 다루려고 합니다.  
  
## 파워앱스와 코파일럿
현재 노코드/로우코드(no-code/low-code) 툴인 [파워앱스(Power Apps)](https://make.powerapps.com)에 전면적으로 보조자로 활용할 수 있는 '코파일럿'이 들어와 있습니다.  
다만, 아쉽게도 한글 프롬프트는 2024년 3월 15일 현재 적용되지 않고 있고 고급기능이라고 할 요소들은 반영이 안되고 있는데요.  
이번 부트캠프에서 어느 수준까지 가능하며, 코파일럿이 어떻게 업무를 변화시킬 것인지에 대해 경험하고 의견을 나누며 정말 '창의력'이 왜 그렇게 중요할 것인지에 대해서 직접 느끼고 실감하는 게기가 되었으면 합니다.

## 준비물 및 참고할 사이트
### 1. SharePoint List(또는 MS Lists)
  이번 핸즈온에서 사용할 'csv' 파일입니다.  
  데이터베이스의 구조와 설계에 해당할 스키마가 들어 있는데, SharePoint에서 가져와서 목록(List)를 만들고 난 후에 이 목록을 통해 손쉽게 앱을 만을 게 됩니다.  
  기본적으로 앱은 데이터를 만들고(Create), 읽어오고(Read), 고치고(Update), 지우는(Delete) 일을 하는데 -이런 일을 영어 앞머리를 따서 'CRUD'라고 하죠?-  자동으로 'CRUD'가 가능한 앱을 목록에서 곧바로 만들어 줍니다.  
  실습에 사용할 파일: [WebinarBookingList.csv](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/blob/main/WebinarBookingList.csv) <- 내려받아 주세요.  

### 2. QR코드 생성
  오픈소스로 QR코드를 생성하는 곳: [https://quickchart.io/](https://quickchart.io/)는 오픈소스로 차트 이미지를 만들어 주는 곳입니다.  
  여기에서는 [QR코드 생성 API](https://quickchart.io/documentation/qr-codes/)를 제공하고 있는데요. 우리가 이번에 활용하게 됩니다.  
  아래와 같이 '홍길동'과 '율도국'을 파이프(|)로 연결한 값을 QR코드에 담아서 이미지로 생성해주고 있습니다.  
  아래 html 주소를 복사해서 브라우저의 새 탭 또는 새 창의 주소에 붙여 넣으면 아래 이미지와 같은 QR코드를 확인하실 수 있습니다.
   
   ```
   https://quickchart.io/qr?text=홍길동|율도국
   ```  

   ![QR코드 예제: '홍길동|율도국'](https://quickchart.io/qr?text=%ED%99%8D%EA%B8%B8%EB%8F%99|%EC%9C%A8%EB%8F%84%EA%B5%AD)
