# GITHUB 워크플로 가이드


## 1. 로컬환경에 프로젝트 만들기
### ✌️ git clone
- 팀협업의 첫 단계는 원본 리포지토리를 복제하는 것입니다! 로컬환경으로 가져와서 작업해보겠습니다!
- 원하는 디렉토리로 이동한 후 터미널에 다음 명령어를 입력하세요.
  `git clone https://github.com/repository-url.git .`
  - `.` 은 현재 위치를 의미합니다
- 최종 목표는, 로컬환경에서 브랜치별로 작업한 후 개발한 내용을 원본 리포지토리(origin)로 push해주는 것입니다. 따라서, 원본 리포지토리와 잘 연결되어 있는 것이 중요합니다. 
- 다음 명령어를 실행하여 원본 리포지토리가 origin으로 연결되어 있는지 확인해보세요.
  `git remote -v` 


## 2. 개발 전 로그 확인하기
### ⚡️ git log
<img width="515" alt="image" src="https://github.com/T3AMARTISAN/collab-practice/assets/122417190/4eaee77a-47e1-4f97-bc57-7c531bde1153">

- 개발을 시작하기 전에 원본 리포지토리의 최신 버전을 가지고 있는지 확인합니다. 나의 프로젝트 버전은 로그에서 HEAD로 파악할 수 있습니다.
- 아래 명령어를 입력하면 전체 브랜치에 걸쳐 커밋내용의 해시를 확인할 수 있습니다. 
  - `git log --oneline --all` // 간단히 보기
  - `git log --all` // 자세히 보기


## 3. 최신 프로젝트 가져오기
### ⚡️ git pull origin main
- main 브랜치에서 최신 프로젝트를 가져오려면 다음 명령어를 실행합니다.
  `git pull origin main`


## 4. 나의 작업 브랜치 만들기
### ⚒️ git checkout - b {branchname}
- 이제 개발을 시작해 봅시다! 작업 내용을 가장 잘 반영해줄 브랜치 이름을 정해주세요.
- 다음 명령어로 브랜치를 생성해줍니다. `feature-create-wallet`에 내가 생성할 이름을 넣어주세요.
  ```
  git checkout -b feature-create-wallet
  ```


## 5. 작업 내용 저장 및 커밋하기
### 🧳 git add, commit
- 깃이 내가 생성한 브랜치에서 변경된 내용을 추적해줍니다. git add 명령어를 통해 변경된 내용을 '스테이징 영역'에 추가하면 선택한 작업 내용이 저장됩니다.
  - `git add .` // 전체파일 추가
  - `git add 파일명` // 특정 파일만 추가

- 저장한 파일을 원본 리포지토리에 올릴 준비가 되었다면 git commit을 실행합니다. 커밋을 통해 로그에서 확인할 수 있는 새 버전을 만들어줍니다.
- **팁: 커밋은 작은 기능 단위로 해주는 것이 효율적입니다.** 변경사항이 많은 경우, 병합할 때 신경써야할 부분도 많아지니까요!
- 커밋메시지는 팀원이 한 눈에 내용을 파악할 수 있도록 핵심을 작성합니다.
  ```
  git commit -m "로그인 기능 추가"
  ```


## 6. Origin에 나의 브랜치 푸시하기
### ✨ git push origin {branchname}
- 이제 커밋까지 마쳤습니다. 다음 단계는 원본 리포지토리에 내가 작업한 브랜치를 병합하는 것입니다. 
- 다음 명령어로 브랜치를 원본 리포지토리로 푸시해줍니다.`feature-create-wallet`에 내가 생성한 이름을 넣어주세요.
  ```
  git push origin feature-create-wallet
  ```


## 7. 원본 리포지토리에 Pull Request 올리기
### 👨🏻‍💻 Create Pull Request
- 팀 협업 시, 풀 리퀘스트를 통해 다음 목적을 달성할 수 있습니다.
  1. 상호 코드리뷰 & 싱크업하기
  1. 당황스러운 코드충돌 줄이기
  1. 전반적인 개발 방향 파악하기
- 원본 리포지토리의 Pull requests 탭에서 PR을 생성할 수 있습니다. 나의 브랜치를 성공적으로 푸시했다면 PR 생성을 할 수 있도록 알림이 표시됩니다.
- Pull Request 양식에 맞춰 작성한 뒤, 팀원을 배정하여 팀리뷰를 합니다.
- 코드 리뷰를 통해 피드백을 주고 받은 뒤, 팀단위로 작업이 마무리되면 풀 리퀘스트를 승인하고 병합(merge)합니다.


## 8. 다음 작업을 위한 리셋!
### 🫧 git checkout main
- 성공적으로 병합을 마치면 로컬환경에서 브랜치를 `main`으로 체크아웃한 뒤, 2번부터 반복해줍니다.
- 내가 생성한 브랜치를 다시 사용할 필요가 없다면 과감하게 삭제해도 됩니다!
     ```
     git branch -d feature-branch
     ```

----

# 🕶️ 팀 컨밴션

효과적인 소통 및 버전관리를 위해 아래 규칙을 따라주세요.

### 브랜치 작명 규칙

생성한 branch를 통해 개발하는 기능이나 목적을 명시해 주세요.
`feature-기능이름`
`fix-오류이름`

### 커밋메시지 규칙

Commit 메시지를 통해 팀원들이 내가 한 작업을 한 눈에 파악할 수 있습니다.
다음 형식을 참고하여 작성해 주세요.

`[Add] 로그인 기능 추가`
`[Modify] LP 토큰 정보 수정`

----

# 자주 하는 실수와 해결 방법

1. **푸시하기 전에 항상 변경 사항 확인**

   - 실수: 변경 사항을 푸시하기 전에 다른 개발자가 푸시한 변경 사항을 놓치는 경우가 있습니다.
   - 해결: 푸시하기 전에 항상 최신 코드를 가져오고 충돌을 해결한 후에 푸시하세요.
     ```
     git pull origin main
     ```

1. **애매한 커밋 메시지 사용**

   - 실수: 커밋 메시지가 명확하지 않아 다른 개발자가 변경 사항을 이해하기 어려울 수 있습니다.
   - 해결: 간결하면서도 명확한 커밋 메시지를 작성하세요.

1. **브랜치를 삭제하지 않고 계속 사용**

   - 실수: 기능 개발이 완료되었음에도 불구하고 브랜치를 삭제하지 않아 저장소가 지저분해집니다.
   - 해결: 브랜치가 더 이상 필요하지 않으면 삭제하세요.
     ```
     git branch -d feature-branch
     ```

1. **보안 관련 정보를 소스 코드에 노출**

   - 실수: API 키, 비밀번호 등을 소스 코드에 포함시켜 보안 문제가 발생할 수 있습니다.
   - 해결: 보안 정보는 환경 변수나 별도의 설정 파일에 저장하고, 해당 파일은 `.gitignore`에 추가하여 깃헙에 업로드되지 않도록 합니다.

1. **풀 리퀘스트 충돌 해결 실패**
   - 실수: 풀 리퀘스트를 병합할 때 충돌이 발생하고 해결하지 못하는 경우가 있습니다.
   - 해결: 충돌이 발생하면 충돌 부분을 수동으로 해결하고 다시 커밋하고 푸시합니다.
