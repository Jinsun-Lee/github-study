---
title: 6.3 브랜치 컨벤션
---

브랜치는 **Jira 이슈와 연결되도록 규칙을 맞춰 생성한다.**       
브랜치 이름만 봐도 **어떤 작업인지 쉽게 이해할 수 있어야 한다.**

```
{prefix}/{jira-issue-key}-{short-description}
```

<br>

예시
```
feat/JIRA-32-rfid-multi-reader
fix/JIRA-40-nav2-goal-error
test/JIRA-56-nav2-drive-test
chore/JIRA-10-docker-update
docs/JIRA-12-readme-update
```

<br><br>

---

## 1. Prefix 종류
feat: 새로운 기능을 추가할 때
```
feat/JIRA-32-rfid-multi-reader
feat/JIRA-21-mqtt-pose-publish
```

<br>

fix: 버그를 고칠 때 (에러 해결, 오타 수정 등 정상 동작으로 만들 때)
```
fix/JIRA-40-nav2-goal-error
fix/JIRA-18-uart-buffer-overflow
```

<br>

test: 테스트 코드를 추가하거나 고칠 때
```
test/JIRA-55-rfid-test
test/JIRA-56-nav2-drive-test
```

<br>

chore: 기능 변경 없이 코드 구조만 개선했을 때
```
chore/JIRA-41-rfid-duplicate-uid
chore/JIRA-10-docker-update
chore/JIRA-15-project-setting
```

<br>

docs: 문서나 주석만 바꿨을 때
```
docs/JIRA-12-readme-update
docs/JIRA-13-git-convention
```

<br>

---

## 2. 이름 작성 규칙
Jira Issue Key 반드시 포함
```
❌ feat/rfid-reader
⭕ feat/JIRA-32-rfid-reader
```

<br>

작업 내용을 짧게 작성        
```
❌ feat/JIRA-32-rfid
⭕ feat/JIRA-32-rfid-multi-reader
```

<br>

단어는 kebab-case 사용       
단어 구분은 `-` 사용
```
❌ feat/JIRA-32-rfidMultiReader
⭕ feat/JIRA-32-rfid-multi-reader
```

<br>

---

# 3. 브랜치 생성 방법
예시: Jira 티켓이 `JIRA-32`일 때, 브랜치 생성
```
git checkout -b feat/JIRA-32-rfid-multi-reader
```

<br>

로컬에서 작업 후, 깃랩에 push
```
git push origin feat/JIRA-32-rfid-multi-reader
```