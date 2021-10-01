# 1. 웹파트 전용 Organization 이용 목적

- 과제 제출
- 코드 리뷰
- 아키이빙
  <br />
  <br />

# 2. 첫 세팅 방법

자신의 이름으로 된 repository를 clone 받아서 이용한다.
<br />
<Br />

## 2.1. clone 이란?

원격의 Git 저장소를 로컬에 복제해오는 명령어이다.  
<br/>

## 2.2. clone 방법

1. 아래 버튼을 눌러 git 저장소 주소를 복사합니다.
   <img src="https://user-images.githubusercontent.com/24906022/134833184-104dca88-2b42-49a1-acc2-34d38aa5b98e.png">

2. cmd(git bash, iterm, cmder 등)를 이용하여 해당 파일을 위치시키고자 하는 폴더에서 <br />
   `git clone <주소> ` 명령어를 입력합니다. <br />
   <img src="https://user-images.githubusercontent.com/24906022/134833418-1c49dad8-2e5c-439b-abfe-7c47ba33fbf5.png">

   - cmd는 local 폴더를 그대로 반영하고 있습니다. `cd <로컬주소>` 를 입력하면, 해당 경로로 들어가고(Change Directory), `../` 를 입력하면 이전 폴더로 돌어갈 수 있습니다. 저 같은 경우는 바탕화면에 있는, projects 폴더 안에 있는 29SOPT에 위치시키고자 했기 떄문에 `cd projects` 를 하고, `cd 29SOPT`를 한 후 `git clone` 명령어를 실행했습니다.<br/><br/>

3. 프로젝트로 들어가서(cd : Change Directory), 프로젝트를 실행시킵니다. (code .)
   <img src="https://user-images.githubusercontent.com/24906022/134833529-c38ad680-947c-43fe-8e93-e42b17d2c09d.png">  
   <br/>

# 3. About git/github

<img src="https://uidaholib.github.io/get-git/images/workflow.png">
<br/>

## 3.1. 4가지 영역

git/github를 사용하면 4개의 영역을 마주하게 된다.

1. working directory (작업하는 공간)
2. staging area
3. local repository (git)
4. remote repository (github)  
   <br />

## 3.2. add란?

working directory에 있는 파일(VS Code에서 변경사항이 발생한 파일)을 staging area로 올리는 명령어.  
즉, 무엇을 repository에 올릴지 정하는 단계.  
다시 말하면 무엇을 commit할 지 정하는 단계.  
<br/>

## 3.3. commit이란?

staging area에 있는 파일을 local repository(git)에 올리는 명령어.  
github가 아니라, git에 올리는 명령어이다.  
git은 local 환경에서 repository 버전관리 해주는 시스템이다.  
github는 이 버전을 온라인 상에 올릴 수 있게 하는 서비스 중 하나일 뿐이다.  
<br />

## 3.4. push 란?

local 에 올려놓은 파일을 remote(github 같은 소스코드 호스팅 플랫폼)에 올릴 수 있도록 하는 명령어  
즉 push 해야 github에 올라가고, 다른 사람이 온라인에서 해당 코드를 볼 수 있다.  
협업을 가능케 하는 것은 github와 같은 서비스이다.  
<br />

## 3.5. pull 이란?<br />

push는 working directory(여러분의 VS Code)와 remote(github)가 다를 때 remote에 올라와 있는 버전을 working directory로 가져오기 위한 명령어이다.  
<br />

# 4. commit 을 왜 하는가?

> 개발 히스토리를 남겨, 이전 개발 기록으로 돌아가기 위하여.

이것이 제대로 이루어지려면, 변경사항이 작고 독립적이어야 한다. 즉, 하나의 기능마다 하나의 커밋을 해주어야 한다. 그러므로, commit message는 기본적으로 하나의 기능이 완수되었음을 설명해야 한다. 가령 웹 개발을 한다고 했을 때, 한 영역을 html 배치하고 하나의 commit을, 한 영역의 css을 추가하고 하나의 commit을, javascript로 하나의 기능을 구현하고, 하나의 commit을. 이렇게 모두 독립적으로 commit 해주는 것이 바람직하다.  
<br />

# 5. Commit Message Convention

commit messagre를 어떻게 적을지에 관한 약속이다. 이는 팀마다 다를 수 있기 때문에, 전적으로 따르지 않아도 괜찮다. 중요한 것은 변경 사항에 대한 설명이 명확하도록 하는 것이다. 그래야 **history rollback**이 용이할 것이다. 이는 협업할 때 중요하게 작용할 것이다.

> `기능(feat)`: 새로운 기능을 추가  
> `버그(fix)`: 버그 수정  
>  `리팩토링(refactor)`: 코드 리팩토링  
> `형식(style)`: 코드 형식, 정렬, 주석 등의 변경(동작에 영향을 주는 코드 변경 없음)  
> `테스트(test)`: 테스트 추가, 테스트 리팩토링(제품 코드 수정 없음, 테스트 코드에 관련된 모든 변경에 해당)  
> `문서(docs)`: 문서 수정(제품 코드 수정 없음)  
> `기타(chore)`: 빌드 업무 수정, 패키지 매니저 설정 등 위에 해당되지 않는 모든 변경(제품 코드 수정 없음)

**Ex) 이렇게 사용할 수 있다.**

```
git commit -m "feat: header 검색 바 html 구현"
git commit -m "feat: 검색 바 스타일링"
git commit -m "style: 주석 삭제"
git commit -m "docs: readme 수정"
```

<br/>

# 6. 과제 제출 방법

> 과제는 매주 금요일까지 새 branch를 파서 Pull Request (PR)로 제출하는 것을 원칙으로 한다.

## 6.1. main/master branch란?

프로젝트 생성하면 처음 생기는 주 브랜치를 의미한다. master branch는 옛날 주 branch 이름이고, 최근에는 main으로 이름이 바뀌었다.  
<br/>

## 6.2. branch란?

<img src="https://t1.daumcdn.net/cfile/tistory/999A7E495B28DBB036">

> 주 브랜치(Master branch)에서 Development branch를 파고 개발하고 main에 합치고, release로 배포하는 일련의 과정을 나타낸 그림.

Software개발시 개발자들은 동일한 소스코드 위에서 신규 개발, 버그 수정 등의 업무를 협업하곤 한다. 이때 동일한 branch로 작업을 하면, 합칠 때에 conflict가 날 수 있다. 이를 방지하기 위해 브랜치(Branch)를 통해 하나의 프로젝트를 여러 갈래로 나누어서 관리할 수 있다. branch를 나누어서 따로 개발을 한 후 나중에 main 브랜치로 합치는 과정을 거친다. 이를 합칠 때에, "저의 코드를 봐주시고, main branch에 반영해주세요" 하는 것이 pull request이다. 그러므로 4명의 개발자가 협업할 때에 하나의 main branch에서 4개의 branch가 뻗어나가고, 각자 다른 기능을 구현한 다음에 pull request를 날리고, 각자 코드를 확인한 후 main에 merge한다.
<br/>
<br/>

## 6.3. branch를 생성하는 방법

`git branch <branch_name>`

과제 제출시 branch 이름은 `assignment1-euijin-kim`과 같이 해주면 된다. branch 이름은 kebab case(소문자 단어들을 - dash로 연결하는 문자표기법)을 흔히 사용한다.
<br/>
<br/>

## 6.4. branch로 이동하는 방법

`git switch <branch_name>`
<br/>
<br/>

## 6.5. branch 생성과 동시에 이동하는 방법

`git switch -c <branch_name>`
<br/>
<br/>

## 6.6. branch를 삭제하는 방법

`git branch -d <branch_name>`
<br/>
<br/>

## 6.6. `git stash`

새 branch에서 작업해야 하는데, 잘못하여 main이나 다른 branch에서 작업한 경우에 자주 사용한다.
이전 commit의 상태로 되돌리고, commit 이후의 모든 파일(add 한 것도)을 잠깐 스택에 저장해두는 명령어.
<br/>
<br/>

## 6.7. `git stash pop`

임시 저장해둔 파일들을 꺼내오는 명령어.

즉, feature/header라는 branch에서 작업을 하다가, feature/footer라는 branch에서 해야할 일이 생겼다고 하자. 이때 commit을 하기엔 하나의 기능을 마치지 않은 단계라고 하자. 이 상태에서 branch를 옮기려고 하면 옮겨지지 않는다. commit하지 않았기 때문에 local 환경에서 기억할 수 없기 때문이다. 그러므로 이 변경사항들을 임시로 저장해둬야하는데, 이를 위해 `git stash` 명령어를 사용한다. 이후 feature/footer에서 작업을 마치고 다시 feature/header로 돌아와서 `git stash pop` 명령어를 사용하면 이전에 임시저장 해둔 변경사항이 다시 돌아오게 되어, 작업을 이어나갈 수 있게 된다.
<br/>
<br/>

## 6.8. pull request 를 날리는 방법

해당 브랜치에 push하고 github repository에 들어가보면 자동으로 pull request 날리겠냐는 메시지가 뜨게 된다.

feature/header branch에서 작업을 하고, `git push feature/header` 하였다면, 아래와 같이 메시지가 뜬다.
<img src="https://user-images.githubusercontent.com/24906022/134860968-5247ac82-5e7e-4683-9131-ccb775da54f9.png">

그리고 `Compare & pull request` 버튼을 누르면 아래와 같은 창이 뜨게 된다.
<img src="https://user-images.githubusercontent.com/24906022/134861317-ef32abc4-7d9a-436d-8a9f-416668240f0d.png">
제목을 입력하고, 내용에는 자신이 이 pull request에서 한 작업, 코드 확인 받고 싶은 부분을 적어주면 된다. 또한 UI 구현 문제가 있거나, 구현 사항을 확실히 보여주고 싶은 경우 img나 gif를 통해서 첨부해주면 좋을 것이다.
<br/>
<br/>

## 6.9. pull request 에서 comment 달고, approve 받기

pull request를 날리면, 해당 pr에서 작성된 코드 변경사항을 볼 수 있고, comment를 달아 칭찬을 해주거나/피드백을 해줄 수 있다. `Files changed`에 들어가서 변경사항을 확인하고, comment를 달아준다.
<img src="https://user-images.githubusercontent.com/24906022/134861942-e84cd47b-500f-4c68-8b8f-414faa0e3857.png">
그리고 오른쪽 위에 `Review changes `버튼을 눌러, 전체 코멘트를 달아주거나, approve 해주거나, Request changes로 수정 요청을 할 수 있다. 그래서 보통 프로젝트 진행 시, 리드 개발자가 approve한 다음에, pull request를 merge할 수 있도록 기능을 추가하기도 한다. 과제에서는 파트장이 approve 한 다음에, merge될 수 있도록 할 것이다.
<img src="https://user-images.githubusercontent.com/24906022/134861725-f376fee2-af3e-4cd0-8bd6-847a9e384895.png">
<br/>
<br/>

## 6.10. branch 내용을 main으로 합치기

과제 제출을 하고, 파트장이 approve하였다면, branch를 main에 merge할 수 있다.
<img src="https://user-images.githubusercontent.com/24906022/134882348-97e2fe41-52c9-4951-87bd-69f3f893fd1f.png">
그리고 이제 해당 브랜치는 필요가 없으므로 `delete branch` 버튼을 눌러, branch를 삭제해주면 된다.
<img src="https://user-images.githubusercontent.com/24906022/134882533-b5b3f69c-286d-4299-9085-a43c05fbffa6.png">
<br/>
<br/>

## 6.11. main에 branch 내용이 붙은 코드를 local 에서 불러오기 (git pull)

특정 branch 내용을 main에 merge 하면, github repository에 잘 반영될 것이다. 하지만 working directory에서는 반영되어 있지 않을 것이다. 이 상태로 작업을 하고 push를 하면, local과 remote(github)간의 차이로 인해 conflict가 발생할 것이다. 그러므로, github의 변경사항을 working directory로 가져올 필요가 있다. 이 명령어가 바로 git pull 이다. main에 있는 내용을 가져온다는 의미에서 `git pull origin main`을 사용한다.

[pr 날리고, comment달고, approve 한 좋은 예시](https://github.com/pa-rang/kyrics-frontend/pull/15)  
<br />

# 7. 마치며.

부족한 글이지만, git과 github가 어색할 여러분을 위해 공들여 쓴 글이니, 어려워도 열심히, 설명이 부족하다면 찾아가면서, 물어가면서 읽어주시면 감사하겠습니다.

---

---

_**2021.09.27 김의진 씀.**_
