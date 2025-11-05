# 🔥 Git + 폴더/파일 관리 + 작업 흐름 올인원 치트시트

---

## 0) 로컬 폴더/파일 기본 작업 (운영체제 명령어)

`ash
# 폴더 생성
mkdir 폴더명

# 폴더 이동
cd 폴더명

# 빈 파일 생성
touch 파일명.txt

# 파일 삭제
rm 파일명.txt              # Mac / Linux
del 파일명.txt             # Windows

# 폴더 삭제
rm -r 폴더명               # Mac / Linux
rmdir /s 폴더명            # Windows

# 파일/폴더 목록 보기
ls                         # Mac / Linux
dir                        # Windows

# 빈 폴더도 Git에서 추적하도록 .gitkeep 사용
mkdir 폴더명
touch 폴더명/.gitkeep
`

---

## 1) Git 저장소 초기화 및 원격 연결

`ash
git init
git remote add origin https://github.com/사용자명/저장소명.git
git remote -v
`

---

## 2) 변경 상태 확인 (필수)

`ash
git status
git diff
git log --oneline
`

---

## 3) 파일 하나만 추가 → 커밋 → 푸시

`ash
git add 파일명
git commit -m 
파일
수정
내용
git push origin 브랜치이름
`

---

## 4) 전체 변경사항 한꺼번에 커밋 & 푸시

`ash
git add .
git commit -m 전체
변경사항
커밋
git push origin 브랜치이름

# 강제 푸시 (⚠ 위험)
git push origin main --force
`

---

## 5) 원격 변경 가져오기

`ash
git pull origin 브랜치이름
# 예: git pull origin main
`

---

## 6) 로컬 변경 완전 삭제 → 원격으로 덮어쓰기 (⚠ 위험)

`ash
git fetch origin
git reset --hard origin/브랜치이름
`

---

## 7) 원격에서 특정 파일만 가져오기

`ash
git checkout origin/브랜치이름 -- 경로/파일명
# 예: git checkout origin/main -- src/App.js
`

---

## 8) 파일 삭제 후 반영

`ash
git rm 파일명
git commit -m 파일
삭제
git push origin 브랜치이름
`

---

## 9) 커밋하지 않은 변경 되돌리기 / 미추적 파일 삭제 (⚠ 주의)

`ash
# 수정된 파일 되돌리기
git restore 파일명

# 추적되지 않은 파일 삭제
git clean -f

# 폴더 포함 삭제
git clean -fd

# 삭제 전 미리 보기
git clean -n
`

---

## 10) 파일/폴더 이름 변경 및 이동 (Git 반영 포함)

`ash
git mv 기존이름 새이름
git commit -m 이름/구조
변경
`

---

## 11) 브랜치 작업

`ash
git branch                   # 브랜치 목록
git checkout 브랜치명        # 이동
git checkout -b 새브랜치명   # 생성 + 이동
git branch -d 브랜치명       # 삭제
git push origin 브랜치명     # 원격 브랜치 올리기
`

---

## 12) 브랜치 병합 (Merge)

`ash
git checkout main
git merge 작업브랜치명

# 충돌 발생 시 → 수정 → 저장 → 아래 실행
git add .
git commit
`

---

## 13) 최근 커밋 메시지 수정

`ash
git commit --amend
`

---

## 14) 안전하게 커밋 되돌리기 (revert)

`ash
git revert 커밋ID
git push origin 브랜치이름
`

---

## 15) .gitignore 예시

`ash
touch .gitignore
`

`	ext
node_modules/
*.log
.env
.vscode/
build/
dist/
`

---

## ✅ 핵심 요약

| 내용 | 명령어 |
|---|---|
| 파일 하나만 반영 | git add 파일명 → git commit |
| 전체 반영 | git add . → git commit |
| 빈 폴더 git 포함 | 폴더 안에 .gitkeep 생성 |
| 완전 되돌리기 (위험) | git reset --hard origin/브랜치 |
| 수정 취소 | git restore 파일명 |
| 미추적 파일 삭제 | git clean -f |

---
