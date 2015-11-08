Bingle-SimpleBGC
=================
## 1. Introduction:
It is based on the SimpleBGC 2.4 serial protocol rev. 0.16.

블루투스 시리얼 통신을 위한 기능을 테스트하며, 테스트 완료 후 본 프로젝트에 적용 할 예정임. 

관련 제조사, 커뮤니티에 많은 질문을 해주기 바람. 알려주는 사람이 없으니..

## 2. Principle:
Android SimpleBGC Serial Protocol Sample requires:
- Android OS 4.0 or higher.
- 32BIT SimpleBGC Board.
 
### 구동 순서
* 현재 테스트를 위하여 초기 command 데이터 전송, real-time data 획득 부분은 주석 처리함.
1. BluetoothConnection - device 이름으로 검색함(line 62 참조)
   
   2-1. 기본 이름 - "bingbing"

2. data read를 위한 thread 생성(SBGCConnector - readSerialData 참조)
3. 메인 액티비티의 sendButton을 누르면 CMD_BOARD_INFO에 해당하는 byte가 보드로 전송됨.(SBGCProtocolUtils - sendCommand참조)

    3-1. command에 해당하는 byte가 잘 생성되고 전송되는지 확인하기
    
    3-2. 송신된 데이터의 양과 outgoing command 호출에 알맞은 incomming command가 수신되는지 확인하기
	
## 3. Getting Android SimpleBGC Serial Protocol Sample:
Refecences Source code is available on github:
https://github.com/fxpal-polly/Android-SimpleBGC

## 4. Build Instructions:
We used Android Developer Tools v22. 
Import as existing Android code into your workspace.	 

## 5. Known Issues:
Not all Serial Commands are implemented.
The code might contain bugs.
hc-06 bluetooth module을 이용한 통신시, 쓰레기 값을
계속 송신함. 보(baud) 레이트를 통일하여 해봐야 될 듯
(SimpleBGC 가이드에서는 115200을 권장함)

## 6. Frequently asked questions:
- Will it work with the BLE Mode, tiny board too? 
