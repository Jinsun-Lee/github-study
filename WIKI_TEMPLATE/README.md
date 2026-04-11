# WIKI_TEMPLATE
GitHub 위키 스타터 템플릿.

<br>

## 용도
GitHub Wiki 는 별도 git 리포(`<repo>.wiki.git`)로 관리되며 `.github` fallback 대상이 아니다. 이 폴더의 파일들은 각 리포의 위키로 **수동 복사** 해서 사용한다.

<br>

## 포함 파일
- [Home.md](Home.md): 위키 홈
- [_Sidebar.md](_Sidebar.md): 사이드바 네비게이션
- [_Footer.md](_Footer.md): 푸터
- [Getting-Started.md](Getting-Started.md): 설치 / 실행
- [FAQ.md](FAQ.md): 자주 묻는 질문
- [Troubleshooting.md](Troubleshooting.md): 문제 해결
- [Glossary.md](Glossary.md): 용어 정리

<br>

## 사용법
대상 리포의 위키를 클론한다.
```bash
git clone https://github.com/<owner>/<repo>.wiki.git
```

<br>

이 폴더의 파일을 위키 리포로 복사한 뒤 커밋한다.
```bash
cp WIKI_TEMPLATE/*.md <repo>.wiki/
cd <repo>.wiki
git add .
git commit -m "[docs] 위키 초기 페이지 추가"
git push
```