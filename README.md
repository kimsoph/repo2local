# 목표
## 로컬 브랜치 이름은 유지: master, local
각 브랜치를 원격 브랜치와 연결:
master → origin/main
local → origin/dev

# 작업 순서 (git switch 사용)
## 1. 원격 정보 업데이트
git fetch origin

## 2. master 브랜치로 이동 후 원격 main과 연결
git switch master
git branch --set-upstream-to=origin/main

## 3. local 브랜치로 이동 후 원격 dev와 연결
git switch local
git branch --set-upstream-to=origin/dev

# 확인
git branch -vv


