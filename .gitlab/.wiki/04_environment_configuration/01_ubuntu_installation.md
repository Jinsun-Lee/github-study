---
title: 4.1 Ubuntu 설치
---






목표: 노트북에 멀티부팅으로 Ubuntu 22.04 설치

<br><br>

## 1. Windows에서 설치 공간 확보
1. 윈도우 검색창에 `하드 디스크 파티션 만들기 및 포맷` 검색
2. 우분투를 설치할 드라이브를 선택하고 `볼륨 축소` 클릭   
3. 축소할 공간을 819,200 MiB (약 800GB)로 설정 후 축소 (`크기는 각자 조정`)

<img width="597" height="366" alt="image" src="https://github.com/user-attachments/assets/170c0c17-c610-4dca-9a40-5afbab900698" />
<img width="597" height="386" alt="image" src="https://github.com/user-attachments/assets/c0d2a18b-941a-4f49-b5cd-f80482ddaa5d" />

<br><br>

## 2. 부팅 USB로 Ubuntu 설치
1. 부팅 USB를 연결하고 PC 전원 종료
2. 전원을 켜고 계속 `F2(또는 DEL) 연타`하여 BIOS 진입
3. Boot Device Priority 설정에서 `UEFI: [USB 이름]`을 1순위로 변경 후 저장 및 종료
4. 부팅 메뉴에서 `Try or Install Ubuntu 선택` -> 오른쪽 Install Ubuntu 클릭
5. Continue 계속 클릭 -> Install Now -> 시간대 South Korea 설정 후 설치 진행
6. 설치 완료 후 Restart Now 클릭
7. 검은 화면에 `Please remove the installation medium...` 메시지가 뜨면 USB를 제거하고 Enter