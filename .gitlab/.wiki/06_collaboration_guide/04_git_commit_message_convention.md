---
title: 6.4 커밋 메시지 컨벤션
---

커밋 메시지는 **다른 사람이 봤을 때 변경 내용을 쉽게 이해할 수 있도록 명확하게 작성**한다.    
**Jira Issue와 자동 연결되도록 태스크 번호와 Smart Commit을 함께 사용한다.**

```
[prefix] 변경 내용 요약
- 작업 내용
- 작업 내용
- Jira태스크번호 #command
```

<br>

예시
```
[docs] 깃허브 내용 정리
- README 구조 정리
- Commit convention 문서 추가
- JIRA-12 #done
```

<br><br>

## 1. Prefix 종류
모든 커밋 메시지는 **변경 종류를 나타내는 prefix를 반드시 사용한다.**     
작업하는 브랜치를 생성할 때 prefix를 포함하니 이를 참고한다.
```
❌ 깃허브 내용 정리
⭕ [docs] 깃허브 내용 정리
```
```
❌ RFID reader MQTT publish 기능 추가
⭕ [feat] RFID reader MQTT publish 기능 추가
```

<br><br>

feat: 새로운 기능을 추가할 때
```
[feat] RFID reader UID MQTT publish 기능 추가
[feat] ROS2 Pose 데이터를 MQTT로 publish하는 노드 추가
```

<br>

fix: 버그를 고칠 때 (에러 해결, 오타 수정 등 정상 동작으로 만들 때)
```
[fix] RFID UID 인식 시 중복 publish 발생 문제 수정
[fix] UART 수신 버퍼 오버플로우 발생 시 데이터 폐기 로직 추가
[fix] Nav2 목표 위치 계산 오류 수정
```

<br>

test: 테스트 코드를 추가하거나 고칠 때
```
[test] Nav2 자율주행 테스트 스크립트 추가
```

<br>

chore: 기능 변경 없이 코드 구조만 개선했을 때
```
[chore] Docker compose ROS2 Humble 이미지 버전 업데이트
[chore] 프로젝트 dependency 업데이트
```

<br>

docs: 문서나 주석만 바꿨을 때
```
[docs] README 프로젝트 구조 설명 추가
```

<br><br>

## 2. 커밋 작성 규칙
커밋 메시지 마지막에 **Jira 태스크 번호와 Smart Commit 명령어를 반드시 포함한다.**
```
[feat] RFID reader UID MQTT publish 기능 추가
- RC522 reader 데이터 수신
- MQTT broker로 UID 전송
- JIRA-32 #done
```
```
[fix] Nav2 목표 위치 계산 오류 수정
- quaternion → yaw 변환 오류 수정
- 목표 좌표 계산 로직 수정
- JIRA-40 #done
```
```
[test] RFID multi reader 인식 테스트 코드 작성
- RC522 reader 3개 동시 테스트
- UID 중복 인식 여부 확인
- JIRA-55
```
```
[docs] 깃허브 내용 정리
- README 구조 정리
- Commit convention 문서 추가
- JIRA-12 #done
```

<br>

커밋 메시지는 **무엇을 했는지 한 문장으로 이해할 수 있도록 작성한다.**
```
❌ 코드 수정
⭕ [fix] Nav2 목표 위치 계산 오류 수정
```
```
❌ 센서 코드 변경
⭕ [fix] IMU 초기화 시 가속도 범위 ±2g로 설정
```

<br>

커밋 1개 = 기능 1개    
하나의 커밋에는 **하나의 기능 또는 하나의 수정만 포함한다.**
```
❌ PWM 제어 로직 개선 및 모터 방향 제어 핀 수정
```
```
⭕ [fix] PWM 듀티 계산 방식 정수 연산으로 변경
- float 연산 제거
- 0~100% → 0~1000 스케일 변환
```
```
⭕ [fix] 모터 방향 제어 GPIO 핀 번호 수정
- PB3 → PB5로 변경
```

<br><br>

## 3. Jira Smart Commit 명령어
`#done`: Jira 태스크를 **Done 상태로 변경**
```
- JIRA-32 #done
```

<br>

`#resolve`: Jira 태스크를 **Resolved 상태로 변경**
```
- JIRA-32 #resolve
```

<br>

`#comment`: Jira 이슈에 댓글 추가
```
- JIRA-32 #comment 테스트 완료
```

<br>

`#time`: Jira 작업 시간 기록(Worklog에 **2시간 작업 기록**이 추가)
```
- JIRA-32 #time 2h
```
