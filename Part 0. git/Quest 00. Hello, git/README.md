# Quest 00. Hello, git


## Introduction
* git은 2016년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics
* git
  * `git clone`
  * `git add`
  * `git commit`
  * `git push`
  * `git pull`
  * `git branch`
  * `git stash`
* GitHub

## Resources
* [git, 분산 버전 관리 시스템](http://www.yes24.com/24/goods/3676100?scode=032&OzSrank=1), 인사이트
* [GitHub 사용 설명서](http://www.yes24.com/24/Goods/17638082?Acode=101), 교학사
* https://try.github.io
* http://pcottle.github.io/learnGitBranching

## Checklist
* 버전 관리 시스템은 왜 필요한가요?
    - IT에서 소프트웨어 개발 프로젝트는 소스 코드가 핵심 자산임. 따라서 소스 코드를 어떤 형태로든 백업하여 분실의 위험에서 보호하고 개정 전후 내용을 파악하여 추후 발생할지도 모를 오류 수정에 대비하는 절차가 필요함
    - 이러한 고민을 해결 해 줄 수 있는 것이 버전관리 시스템임
    - 아래와 같은 예를 통해 버전관리 시스템이 필요한 이유를 생각할 수 있음
        - 무언가 잘못되었을 때 복구를 돕기 위하여
        - 프로젝트 진행 중 과거의 어떤 시점으로 돌아갈 수 있게 하기 위하여
        - 여러사람이 같은 프로젝트에 참여할 경우, 각자가 수정한 부분을 팀원 전체가 동기화하는 과정을 자동화하기 위하여
        - 소스 코드의 변경 사항을 추적하기 위하여
        - 소스 코드에서 누가 수정했는지 추적하기 위하여
        - 대규모 수정 작업을 더욱 안전하게 진행하기 위하여
        - 가지내기(Branch)로 프로젝트에 영향을 최소화 하면서 새로운 부분을 개발하기 위하여
        - 접붙이기(Merge)로 검증이 끝난 후 새로이 개발된 부분을 본류(trunk)에 합치기 위하여
        - 많은 오픈 소스 프로젝트에서 어떠한 형태로든 버전 관리를 사용하고 있으므로
        - 코드의 특정 부분이 왜 그렇게 쓰여 졌는지 의미를 추적하기 위하여
* git 외의 버전관리 시스템에는 무엇이 있나요? git은 그 시스템과 어떤 점이 다르며, 어떤 장점을 가지고 있나요?
    - CSV (Concurrent Versions System)
        - 가장 오래된 버전관리 시스템으로 많은 사용자들에게 검증되어 있는 시스템이다.
        - posix계열의 장비는 물론 windows까지 대부분의 운영체제를 지원한다.
    - SVN (Subversion)
        - atomic commit을 지원함으로 소스 커밋 실패시 rollback이 보장됨
        - 여러 파일을 한번에 커밋해도 한개의 revision이 올라가며 해당 revision으로 버전관리가 가능하다
        - 트리별, 파일별로 접근 제어가 가능하다
* git의 `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?
    - clone
        - 원격저장소를 복제하여 저장소를 생성함, 폴더명은 생략가능
        - git clone <저장소주소> <폴더명>
    - add
        - git이 새 파일이라 인식하고 지켜보게 한다. add를 하게 되면 git의 저장소 'snapshot'에 포함된다.
        - git add <파일명>
    - commit
        - 변경사항을 만든 후 저장소의 'snapshot'을 생성함.
        - git commit -m <message>
    - push
        - 로컬 컴퓨터에서 작업하고 커밋을 원격 저장소에 저장하기 위한 명령여
        - git push
    - pull
        - 로컬 컴퓨터에서 작업할 때 작업하고 있는 저장소의 최신버전으로 업데이트 하기 위해 사용하는 명령어
        - git pull
    - branch
        - 여러 협업자와 작업할 때, 자신만의 저장소를 원할 때 사용함. 새로운 branch를 만들고 자신만의 변경사항과 파일 추가등의 커밋 타임라인을 만듦.
        - git branch <repository nickname>
    - stash
        - unstaged 상태인 변경사항을 일시적으로 백업하고 작업디렉토리를 깨끗한 상태로 유지. 다시 이전 상태로 되돌리려면 git stash pop 명령어를 수행.
        - git stash save || git stash pop

## Quest
* github에 가입한 뒤, [이 커리큘럼의 github 저장소](https://github.com/KnowRe/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
* [GitHub Desktop](https://desktop.github.com/)을 다운받아 설치합니다.
* Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
  * 앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
* 이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
* `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.
