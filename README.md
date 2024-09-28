# 각 장치 setup 명령어
    - 중앙관제 시스템 : ./make_center
    - 출입통제 시스템 : ./make_edge
    - 회사출입 게이트 : ./make_gate
        - 아래 "회사출입 게이트 setup(컴파일) 시 주의사항" 꼭 읽어보기
        
=====================================================================
# 각 장치의 필요 라이브러리
    - 중앙관제 시스템 : /Center, /Network, /Utilities
    - 출입통제 시스템 : /Edge, /Network, /Utilities
    - 회사출입 게이트 : /Gate 

=====================================================================
# 회사출입 게이트 setup(컴파일) 시 주의사항
    - 아래의 작업들이 선행되어야 함
        - Arduino CLI 설치
            - `sudo apt update`
            - `sudo apt install arduino-cli`
        - 아두이노 우노 보드 설정
            - `arduino-cli core install arduino:avr`
        - 보드 연결 및 설정
            - `arduino-cli board list
            - arduino-cli board attach --port /dev/ttyACM0 arduino:avr:uno

=====================================================================
# 설치파일 구성
    vision
    ├── Center
    │   ├── header
    │   │   ├── MonitoringSystem.h
    │   │   └── ONVIFClient.h
    │   └── source
    │       ├── MonitoringSystem.cpp
    │       └── ONVIFClient.cpp
    ├── Edge
    │   ├── header
    │   │   ├── AccessControlSystem.h
    │   │   ├── GateControl.h
    │   │   ├── ONVIFAccessControl.h
    │   │   ├── SensorManager.h
    │   │   └── _RulesManager.h
    │   └── source
    │       ├── AccessControlSystem.cpp
    │       ├── GateControl.cpp
    │       ├── ONVIFAccessControl.cpp
    │       ├── SensorManager.cpp
    │       └── _RulesManager.cpp
    ├── Gate
    │   ├── header
    │   │   └── Motor.h
    │   └── source
    │       └── Motor.cpp
    ├── Makefile
    ├── Network
    │   ├── header
    │   │   ├── ClientHandler.h
    │   │   ├── Mutex.h
    │   │   ├── Server.h
    │   │   └── ThreadPool.h
    │   └── source
    │       ├── ClientHandler.cpp
    │       ├── Mutex.cpp
    │       ├── Server.cpp
    │       └── ThreadPool.cpp
    ├── Utilities
    │   └── Utilities.h
    ├── docs
    │   ├── FlowChart.drawio
    │   ├── README.md
    │   └── goal.txt
    └── main.cpp