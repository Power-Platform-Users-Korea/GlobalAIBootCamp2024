# SharePoint List에서 앱만들기
## 1. SharePoint로 이동하기
여러 방법이 있지만 우리는 기본적으로 [Microsoft 365](https://www.microsoft365.com/)에서 출발하겠습니다.  
위 주소를 눌러서 핸즈온용으로 부여받은 계정(account)와 비밀번호(password)로 '로그인(Sign in)'을 해주세요.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/ee917424-fa89-4d61-8886-16cf31710a74)

로그인하신 후에 왼편의 '모든 앱(Apps)'를 눌러 이동합니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/8b5d3c96-2643-42b8-b9b2-52fadd61ff40)

가운데에 'SharePoint'가 보이시죠? 이걸 클릭합니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/9145027e-13fe-46fe-9475-f97af5531a13)

## 2. SharePoint List 만들기
SharePoint에 접속하시면 왼편에 메뉴들이 나와 있습니다.  
거기서 목록(List)를 만들어 보겠습니다.  

동그라미 안에 '+' 모양의 메뉴를 누릅니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/980a6b23-0a54-4abd-ba9d-87d2d9b88298)

다음으로 목록(List)를 눌러 새로운 목록(List)를 만듭니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/67d59e8b-72ea-40d0-a0e9-eb87c9c52354)

여러방법으로 List를 만들 수 있지만, 이번 핸즈온에서는 미리 내려받은 파일을 가져오는 방법으로 하겠습니다. 
그리과 같이 **From CSV**를 눌러 미리 내려받은 [WebinarBookingList.csv](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/blob/main/WebinarBookingList.csv) 파일을 업로드 하도록 하겠습니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/02a34788-37ad-4073-8f8f-92b0b2875e0e)

**Upload file**을 툴러 내려받아둔 파일 [WebinarBookingList.csv](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/blob/main/WebinarBookingList.csv)을 업로드 합니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/fa2a7b6a-8c8d-4d94-8583-9ebf48ab8a2c)

![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/33efb0db-1bc6-4a97-81bb-2efbb8780769)

이번 핸즈온에서는 파일 스키마가 있는 csv 파일을 사용하고 있어서 따로 확인할 필요는 없지만, 일반 엑셀 파일을 가져오는 경우에는 각 컬럼별 속성(붉은 색 테두리 쳐둔 부분)을 잘 확인하셔야 합니다.  
출석여부를 다루는 **Attendance** 컬럼은 **Choice**로 해둔 점을 눈여겨 봐주세요.  
'다음(Next)'를 눌러 csv에서 SharePoint List를 만듭니다.
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/9326058e-dd2f-4d66-87ed-2d52ee5681ff)

> 중요: 이번 실습에서는 '내 목록(My lists)'에 '목록(list)'을 생성하지만, 협업을 할 경우에는 MS Teams의 해당 팀 또는 SharePoint Group에서 만들게 됩니다. 이 때 사용자별 접속권한 등을 잘 고려하셔야 합니다.  

적당한 이름을 사용하셔서 목록(list)를 만드시면 됩니다. 여기에서 '목록'은 SharePoint List(또는 MS Lists)의 list를 말합니다.  
저는 'WebinarBookingList_01'이라고 이름을 바꿔서 작업하도록 하겠습니다. 이미 같은 이름의 목록을 만들었기 때문입니다.  
핸즈온에서는 본인 계정을 추가해주시는 것이 좋을 수 있습니다. '내 목록'에 저장하고, 해당 목록에서 곧바로 앱을 만들기 때문에 큰 문제가 없지만 좋은 습관은 나중에 좀 더 좋은 결과를 낳게 될겁니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/7d678f3d-9eb7-4f27-8465-e1a4a1d91c8c)

짜잔!  
내 목록(My lists)에 저장하면 SharePoint가 아닌 Microsoft Lists라는 곳에 저장이 되어 있는 걸 눈썰미 좋은 분들은 확인하실 수 있습니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/6a455bfc-df85-4e34-8fc6-014539d8551c)

> 엄청중요: Attendance 라는 컬럼이 Choice 이기 때문에 나중에 출석체크를 확인할 때 Boolean으로 처리가 어렵습니다. 그래서 Attendance_Status라는 'Yes/No' 타입의 컬럼을 만듭니다.

나중에 출석체크할 때 토글로 사용할 계획입니다.
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/3242e048-cdca-4b49-9873-3bf2d4eaa0e5)


## 3. SharePoint List에서 앱 만들기

이제 앱을 만들어 봅시다.  
목록(list) 위에 있는 메뉴에서 **"Integrate > Power Apps > Create an app"** 순서로 앱을 만듭니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/7f63bb68-7a57-4f85-8dce-ae26c14f7ec3)

잠깐 기다리면... 짜잔 짜잔!!  
디자인이 좀 밋밋하지만 CRUD용 앱이 만들어졌습니다.
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/311eae5b-e550-4bc0-8cb4-a172dd6dfc5d)

이렇게 만들어진 곳을 '캔버스(Canvas)'라고 합니다. 그림을 그리는 것처럼 앱을 만들 수 있다는 뜻이겠죠? 이번 핸즈온은 파워앱스를 다루는 게 아니라 코파일럿을 어느정도 활용할 수 있는 지를 다루는 거라 상세 설명은 하지 않겠습니다.  
오른쪽 위에 보시면 '코파일럿' 메뉴(![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/48af9785-1932-4fb7-adcd-0d465c6916e7))가 보이실 겁니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/1649b048-ad63-41c5-9db0-7ffa759612ec)

우리가 활용할 녀석입니다.

## 4. Power Apps Canvas에서 Copilot 써보기
먼저 상단에 있는 코파일럿 버튼을 눌러 해당 기능을 활성화 합니다.
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/c667eb1f-bdb4-4137-8ecd-26a758ad5a33)

### Home Screen 만들기
채팅창(프롬프트 입력창)에 '한글'로 다음과 같이 입력해볼까요?  
```
'Home'이란 스크린을 새로 추가해주세요.
```
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/63fba8a8-27a2-4fda-b176-08c6d2847901)

어랏! 한국말도 알아듣네요?  
Home이 추가되었다고 답을 하고 있고, 왼쪽에 가보시면 'Home'이란 스크린이 생성되어 있습니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/31060d17-c8fc-4eb8-a54c-d61b0d8bfe8e)

QRScreen 이란 이름으로 스크린을 추가하려고 했는데, 'Screen2'라고 제멋대로 생성해버리네요.  
```
Add a screen of QRScan, please
```
그래서 이름을 바꾸는 프롬프트를 띄웠는데, 그것도 잘 먹지 않습니다.ㅠㅠ  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/0cc8b022-cc97-4462-84c8-a0d6c4a97662)

다시 'QRScan'이라는 스크린을 새로 추가해달라고 했던 프롬프트 아래의 'Undo'를 눌러 되돌리기를 한 후에 다시 한국어로 QRSCan이란 이름의 Screen을 새로 추가해달라고 해보니 잘 작동합니다.
```
QRScan이라는 이름의 Screen을 새로 추가해주세요.
```
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/206ef3b7-5a23-4872-be0a-dddfe75a2623)

다음으로 'Home' 스크린을 Tree View에서 가장 위로 올리고 싶은데(move up) 아직은 이 명령어는 한 번도 성공하지 못했습니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/fcc10440-4a4e-45f0-9909-819ad2eeeba6)

그래서 손수 올려보도록 하겠습니다. 가장 위에 위치한 스크린이 앱을 실행했을 때 첫 화면이 되기 때문에 이 작업은 생각보다 중요합니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/76b1be74-527a-4163-83bd-badeb071e325)

가장 위에다가 Home 스크린을 뒀죠?  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/6b29412c-b31b-4255-9118-110eb95263cb)

## 5. Home 스크린에 미디어 추가 및 버튼 추가
> 준비사항: 앱의 Home Screen에 추가할 이미지 파일을 내려받아주세요. [Home Screen용 이미지 파일 내려받기](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/blob/main/globalai.bootcamp.seoul.2024.jpeg)

Power Apps Canvas의 왼편 메뉴 가운데 Media(![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/686aa920-161c-4a39-abfa-d92ee40281f8))
를 선택한 후에 내려받은 이미지 파일을 해당 Media에 올립니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/c8753744-92f8-4d6e-8b00-a4968e1f9a6f)

해당 이미지 파일을 잘 올리셨으면, 아래와 같이 올려놓은 이미지 파일을 Home Screen에 끌어다가 배치하고 크기를 조정합니다.  
![msedge_24031521](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/34f794c9-98a9-456f-aef3-0e56b755bd80)

자, 이제 다시 코파일럿과 놀 시간입니다.  
홈페이지에서 명단이 있는 스크린(BrowseScreen1)과 QR코드를 스캔할 스크린(QRScan)으로 이동하는 버튼을 추가하려고 합니다.  
왼편 메뉴에서 Tree View(![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/e087452b-d8aa-4540-b94b-1c8d406fad35)
)로 이동한 후에 오른쪽의 코파일럿을 만나러 갑니다.  

```
'BrowseScreen1'으로 이동하는 '명단확인'이란 버튼과 'QRScan'으로 이동하는 'QR스캔'이란 버튼을 추가해주세요.
```
라고 했더니 오류가 나타나네요.  

이번에는 영어로 프롬프트를 만들어서 실행했더니 함수가 틀리게 추가되었습니다.
```
Add 2 buttons. A button title is "명단확인" to navigate to BrowseScreen1, when the button is on select mode. The other button title will be "QR스캔" to navigate to QRScan.
```
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/61bb4a1b-3140-4cfa-8fd9-6c4230856207)

우선 버튼위치를 아래로 옮긴 후에 내용을 수정해보도록 하겠습니다.  
함수에 오류가 있으면 오른쪽 상단에 청진기 모양(![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/63ad7d2c-b1f9-479a-bde4-d22baa390004)
)의 앱 체커가 빨간 점을 찍고 알려줍니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/22871573-32ef-4ee3-b5c6-d3a2d18fb2c0)

'Selected'라는 게 모르는 내용 또는 지원안되는 함수라고 하죠?  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/4d150565-c54b-4460-80f2-b0ac5ac52d03)

새로 프롬프트를 추가해봅시다.  
```
App checker says that "Selected" is an unknown or unsupported function. Fix the error of the 2 buttons to navigate each destination.
```
라고 했더니 "Button1"을 못찾겠다고 합니다.  

```
App checker says that "Selected" is an unknown or unsupported function. Fix the error of button1 and button2 in Home screen to navigate each destination.
```
구체적으로 버튼 이름을 지정해서 고쳐달라고 했더니 아주 잘 고쳐주네요.  
App checker에 빨간 색 점도 사라졌고, 버튼에 붙어 있던 빨간색 X 모양의 경고도 사라졌습니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/daf9631c-6d3b-483e-a45d-2469f6b48052)

버튼 조정을 해보겠습니다.  
이건 프롬프트로 설명하는 것보다 직접 손으로 조작하는 게 더 빠르겠습니다.  
버튼 두개를 모두 선택한 후에(두 버튼 바깥 여백에서 마우스 왼쪽 버튼을 누른채 두 버튼을 지정하면서 선택하실 수 있습니다)  Size를 각각 160으로 바꿔줍니다. 그리고 Boader radius의 값을 '10'에서 '100'으로 바꿔봅니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/e5ab8ce8-178d-493c-a46e-126b3f9da141)

## 6. Home Screen으로 이동하는 아이콘 추가하기
이제 BrowseScreen1과 QRScan으로 이동하는 버튼을 Home에서 만들었으니 각 스크린에서 Home으로 가는 기능도 추가해야겠죠?  
home icon을 추가했습니다. 원래는 상단에 있는 Insert 메뉴에서 추가합니다만, 이번에는 코파일럿에게 시켰습니다.  
```
Add a home icon to BrowseScreen1
```

그리고, QRScan에도 home icon을 하나 더 추가해달라고 합니다.  
```
Add a home icon to QRScan, either.
```
그랬더니 이름에서 충돌이 있을 수 있다며 Icon2라는 이름으로 아이콘을 추가했다고 하네요.  근데 home icon이 아닌 화살표를 추가했길래 다시 프롬프트를 보냈습니다.  
Power Apps에서 각 버튼, 아이콘, 텍스트 레이블 등은 모두 고유한 이름을 가집니다. 따라서, 같은 이름을 사용하면 오류가 생기니 코파일럿의 제안은 잘 기억하시기 바랇니다.  

다시 프롬프트를 작성해서 코파일럿이 일할 기회를 줘보시죠.
```
Add another home icon to QRScan, the title of the icon will be "iHomeQR".
```
iHomeQR이란 이름으로 home icon을 추가해달라고 했는데, Icon3라는 이름으로 추가해버렸네요.  
그래서 아래 그램의 3번과 같이 싫어요를 누른 다음 피드백을 보냈습니다. 뭔가 일러바치는 기분이 들었습니다만 더 나은 서비스를 위해서 도움이 되길 바랍니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/b071306a-ca67-4ab5-ac91-15c412448ce0)

나머지 미세한 색깔 및 위치 수정은 프롬프트보다 손으로 직접하는 게 훨씬 빨라서 직접 하도록 하겠습니다.  
다만 해당 home icon 들에게는 Navigate 함수를 사용하면 쉽습니다.  
```
Navigate(Home)
```
![msedge_24031522](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/4e5b8e39-f9b5-4fd2-9259-07c9efa80580)

## Barcode Reader 추가하기
아직까지는 Bardode reader를 추가하는 프롬프트는 작동하지 않는 것 같습니다. 제가 몇달째 사용하지만 2024년 3월 15일 현재는 거듭해서 오류가 나오네요.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/d4969b26-d9da-4111-939f-641ad12e7f5d)

QRScan 스크린에서 위 메뉴로 이동해서 Inser를 누른 후에 검색창에 'bar'까지만 입력했는데, Barcode reader가 나타나네요. 클릭해서 추가합니다.  
![image](https://github.com/Power-Platform-Users-Korea/GlobalAIBootCamp2024/assets/83335854/589019c3-7a9b-4da5-8a9c-d1cc235264db)

저는 오른쪽 위에 추가했습니다.  그리고 텍스트를 "QR코드 스캔"이라고 고쳤습니다.
역시 'On Scan' 모드가 중요합니다.  함수를 생성하는 방법이 중요한데 해당 함수까지는 만들어 내지 못하는 것 같습니다.  

## 8. Microsoft Edge의 Bing Copilot과 ChatGPT 활용하기
Power Apps의 코파일럿은 프롬프트 글자수가 제한적입니다. 충분한 요구사항을 전달할 수가 없습니다.  
그래서 다음과 같은 프롬프트를 '빙(Bing)'의 코파일럿과 챗지피티(ChatGPT)에 적용해보겠습니다.
```
Power Apps의 Barcode reader 기능을 활용해서 QR Code의 값 가운데 일부를 추출한 다음 해당 추출한 값을 vName이란 Text Label에 표시하려고 합니다.
QR Code에서 스캔한 값의 구조는 "https://quickchart.io/qr?text=name|organization"과 같습니다.
여기에서 name에 해당하는 값을 추출해서 vNameValue라는 변수에 저장하고 vName이라는 Text Label에서는 해당 변수에 저장된 값을 읽어서 표시하면 됩니다.
Barcode reader의 On Scan 모드에 적용할 함수를 만들어 주세요.
```

### 8-1. Bing Copilot 활용하기
Edge에 기본적으로 적용되는 코파일럿의 답변입니다.


Power Apps에서 Barcode Reader 기능을 활용하여 QR 코드에서 일부 값을 추출하고 해당 값을 Text Label에 표시하는 함수를 만들어드리겠습니다.
> 1. **QR 코드 값 추출**:
>    - QR 코드의 구조가 "https://quickchart.io/qr?text=name|organization"과 같다고 하셨으므로, 여기서 `name`에 해당하는 값을 추출해야 합니다.
>    - QR 코드를 스캔한 후, 해당 URL에서 `name` 값을 추출하는 방법은 다음과 같습니다:
>    - QR 코드 스캔 결과를 `BarcodeReader1.Barcodes`로 가져옵니다.
>    - 이후 `First(BarcodeReader1.Barcodes).Value`를 사용하여 `name` 값을 추출합니다².
> 2. **Text Label에 값 표시**:
>    - 추출한 `name` 값을 `vNameValue`라는 변수에 저장합니다.
>    - Text Label인 `vName`에서 `vNameValue` 값을 읽어 표시합니다.

```PowerApps
// OnScan 이벤트에서 호출되는 함수
// QR 코드 스캔 결과에서 'name' 값을 추출하여 Text Label에 표시
ClearCollect(
    colBarcodes, // 임시 컬렉션 생성
    BarcodeReader1.Barcodes // QR 코드 스캔 결과 가져오기
);

// 'name' 값을 추출하여 변수에 저장
Set(
    vNameValue,
    First(colBarcodes).Value
);

// Text Label에 저장된 값 표시
UpdateContext({vName: vNameValue})
```

> 위 함수를 Power Apps의 Barcode Reader의 On Scan 이벤트에 적용하시면 됩니다. 이제 QR 코드를 스캔하면 해당 값이 Text Label에 표시될 것입니다.¹²  
> Source: Conversation with Bing, 3/15/2024  
> (1) Master the New Power Apps Barcode Reader Control: Boost Your Apps with Single, Auto .... https://www.powerapps911.com/post/master-the-new-power-apps-barcode-reader-control-boost-your-apps-with-single-auto-and-multi-scan.  
> (2) Solved: Getting the value of a QR Code from a Barcode Read... - Power Platform Community. https://powerusers.microsoft.com/t5/Building-Power-Apps/Getting-the-value-of-a-QR-Code-from-a-Barcode-Reader-and/td-p/2202627.  
> (3) Solved: Splitting Data recieved from Qr code and placing i... - Power Platform Community. https://powerusers.microsoft.com/t5/Building-Power-Apps/Splitting-Data-recieved-from-Qr-code-and-placing-it-in-variables/td-p/634795.  
> (4) Attendee Check-In: Build Canvas App for scanning QR-code. https://ulrikke.akerbak.com/2021/09/20/attendee-check-in-with-canvas-power-apps/.  

### 8-2. 챗지피티 활용 답변

```
If(
    CountRows(BarcodeReader1.Barcodes) > 0,
    Set(
        vNameValue,
        First(Split(Last(Split(First(BarcodeReader1.Barcodes).Value, "=")).Value, "|")).Value
    )
);
```

결국 "|"를 기점으로 둘을 나눠서 이름을 가져와야 하는 것은 같습니다. 하지만, Bing의 코파일럿은 "|"을 분리하는 내용이 없습니다.

Bing 코파일럿이 내놓은 답변을 살짝 수정하면 다음과 같습니다.  
```Power Apps
ClearCollect(
    colBarcodes, 
    BarcodeReader1.Barcodes
);

Set(
    vNameValue,
    First(Split(First(BarcodeReader1.Barcodes).Value, "|")).Value
);

UpdateContext({vName: vNameValue})
```

## 9. 마무리
### 9-1. QR 코드 스캔한 값 확인하기
Text Label을 4개 추가한 후 '이름'과 '소속'을 각각 키(key)와 값(value)으로 나타낼 수 있게 합니다.  
Lookup 함수를 사용합니다.  
### 9-2. QR 코드 스캔한 사람의 출석상태 체크
Toggle 버튼으로 손쉽게 출석여부를 확인하고 상태값을 업데이트 합니다.  
Toggle 버튼에는 "Yes/No" 타입의 "Attendance_Status"라는 컬럼을 활용합니다.  
Toggle 버튼과 일반 버튼을 추가해서 Patch 함수를 이용해 상태를 변경하게 합니다. 
