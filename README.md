🎯 최종 목표
로컬 브랜치	원격 브랜치 (GitHub)	연결 상태
main	origin/main	✅ 추적 연결 완료
dev	origin/dev	✅ 추적 연결 완료

🪜 전체 단계 (정석 방식)

✅ 1단계: 현재 브랜치 확인

git status
출력에서 현재 브랜치가 master임을 확인하세요.

✅ 2단계: master → main 으로 브랜치 이름 변경

git branch -m master main
🔹 -m은 브랜치 이름을 변경하는 명령입니다.
🔹 현재 브랜치가 master여야 실행 가능합니다.

✅ 3단계: 원격 정보 가져오기

git fetch origin
🔹 원격 저장소에 있는 브랜치 목록(origin/main, origin/dev)을 로컬에 최신화합니다.

✅ 4단계: main 브랜치와 원격 연결

git branch --set-upstream-to=origin/main main
🔹 이제 git pull, git push 시 origin/main으로 자동 동기화됩니다.

✅ 5단계: 변경된 main 브랜치 푸시

git push
🔹 오류 없이 origin/main에 푸시됩니다.

✅ 6단계: local → dev 브랜치도 연결

git switch local
git branch -m dev               # local → dev 이름 변경
git branch --set-upstream-to=origin/dev dev
git branch -m dev는 현재 브랜치 이름을 dev로 변경
--set-upstream-to=origin/dev는 자동 추적 설정

✅ 7단계: dev 브랜치도 푸시

git push
🧾 최종 결과 구조

📦 로컬 저장소
├── main ──▶ origin/main
└── dev  ──▶ origin/dev

원하신 **"정석 연결 구조"**로 완성되었습니다.
원격과 로컬 브랜치가 정확히 매칭되었고, 추적 브랜치도 설정되어 있어 이후 git pull, git push가 간단해집니다.