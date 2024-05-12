# Nextjs 14버전으로 Z.com 클론코딩 하기 학습 기록

# 섹션 0 인트로 
## Next.js 13 이후에 바뀐 점

- Major 라이브러리 버전도 올라갔다.
- 2년간 변화에 대한 업데이트가 이루어질 예정이다.
- 13버전부터 App Router와 Pages Router 두 가지로 나뉘어진다.
- App Router가 Pages Router를 새롭게 업데이트한 부분(신기능이 여기 대부분 있을 것이다.)
- App Router에는 버그 + 실험적인 기능들도 있어서 완벽하지 않다.
- 13버전부터는 Directory 기능이 많이 변경되었다.
- react 18 버전을 쓰기 때문에 Server Component를 적극 사용할 수 있다.
    - 완성된 HTML을 서버에서 보내줄 수 있도록.
    - 서버에서 혼자 처리하다 보니 부담이 될 수 있기에 캐시를 적극적으로 활용할 수 있다.
- 굳이 Next로 서버를 구성하지 말고 서버는 따로 두는 것을 추천

## 클론 코딩의 장단점

- [Z.com](http://Z.com) ㅋㅋㅋ
- 장점
    - 훌륭한 결과물을 직접 만들어볼 수 있다는 것
    - 새로운 기술들을 습득할 수 있다.
    - 완성된 결과물이 있기 때문에, 만들 수 있다는 가능성이 있다는 것. 많은 시도를 해보고 공식문서를 꼼꼼하게 확인하면서 직접 완성해보는 과정 자체가 좋은 경험이 될 수 있다.
    - 공식문서의 해석내용과 적용한 방식이 맞는지 확인할 수 있다는 것
- 단점
    - 뇌빼고 따라하기 금지.
    - 생각하고 왜 이렇게 구조를 짜고 코딩을 할까에 대한 생각이 필요
    - 클론코딩한 결과를 포트폴리오로 활용하지 말것. (너무 많은 수강생이 들은 경우 특이점도 없고 메리트가 없다.)

## 리액트 압축 요약 강좌

- 리액트에 대해서는 강좌를 들은 적이 있어서 Skip

## 에러 잘 질문하는 법 & 삽질 덜 하는 법

### 에러 확인하는 법

- 요즘 프로그래밍은 에러를 잘 해결하는 것이 시간을 아끼는 방법
- 에러를 해결하는 그 짜릿함을 즐겨야 한다.
- 에러메시지를 번역을 잘 하는 것이 중요하다.
1. 에러 메시지 확인/번역 필수
    - 에러메시지 자르지말고 위에서부터 천천히 볼 것(Fail, Error)
    - Stack Trace를 통한 에러 위치를 파악하고 해당 부분에서 해결 가능 여부를 확인하기
    - 여러 줄에서 에러가 발생한다면 모든 부분에서 의심하기
2. 에러메시지가 내 코드 에러인지, 라이브러리 에러인지 분류
    - 파일명:줄:칸 뜨면 내 코드이고 내 코드에러라면 구글/스택오버플로우/챗GPT 등 검색 및 문제 파악 시도(번역 잘 해서 확인하기)
    - 라이브러리 에러의 경우에는 그 라이브러리 github issue를 보는게 더 좋은 결과를 얻을 가능성이 있다.
        - 하지만, 내가 잘못 써서 발생했는지, 라이브러리 자체 문제인지도 파악해야 한다.
        - 과거 버전으로 돌려보기, 라이브러리 코드 직접 까서 확인해서 PR날리기, issue건의, patch-pakage를 통해서 내가 수정한 라이브러리 코드 반영하기
    - 하나의 해결책을 시도해보고 안되면 되돌린 후 다음 해결책을 실행하자.
3. 에러가 언제부터, 어디서 발생했는지 모르는 경우
    - 과거 내가 했던 것들을 Git Log에서 커밋 단위로 되돌려보고 발생한 시점을 찾는 것이 좋다.
    - squash 보다 세세하게 커밋을 여러개 남겨주는게 좋을 수 있다.(작업 양이 많은 경우 되돌리기 좋다)
    - 이렇게 에러가 발생하는 시점을 추적한 후 해당 부분에 대한 수정 작업을 진행한다.

### 질문 잘 하는 법

- 잘못 질문하는 것일수도 있기 때문에, 잘 질문하는 것이 중요하다.
- 나쁜 질문 하는 방법
    - 질문해도 되나요?
    - 돌려서 질문한다.
    - 엉뚱한 곳에 질문을 올린다.
    - 구체적으로 질문 제목을 작성하지 않는다.
    - 어떤 작업을 하는 코드인지 말하지 않는다.
    - 에러메시지를 일부 혹은 올리지 않는다.
    - 코드를 보여주지 않는다.
    - 포맷이 엉망인 코드를 올린다.
    - 이미 시도해본 것들을 말하지 않는다.
    - OS나 버전 등을 알려주지 않는다.
    - 코드를 짜달라고 요청한다.
- 에러 메시지 스스로 번역하기
- 에러 메시지 잘라서 올리지 않기
- 코드 같이 올리기
- 응용하면서 막히는 부분, 여러 선택지 중 조언이 필요한 부분, 제로초의 경험이 궁금한 부분에 대한 질문은 ok 회사 질문은 no
- 강좌마다 남의 질문도 확인해보기

## 이 강의를 효율적으로 듣는 방법

- 따라치는 강의가 아니다.
- 강의 코드가 많이 늘었기 때문에, 코드를 깃헙에서 클론하여서 따라가는 것이 중요하다.
- 챕터 별로 완성된 코드를 제공하고 있기에, 하나의 묶음에 대한 코드를 참고하면서 강의 수강하기.
- 수강생 강의노트도 확인해보면 좋다.
- 스스로 만들어보고 완성된 코드를 확인하는 형태로 진행하는 것도 좋은 방법이 될 것이다.

# 섹션 1 기획자와 디자이너가 기획서를 던져주었다.
## Next 프로젝트 시작하기

- 화면을 어떻게 만들것인가?
    - 기획서가 없기 때문에 완성된 화면을 보면서 어떻게 할지 구상해보기
    - 상호작용에 따라 주소가 바뀐다는 부분
    - 새로고침하면 어떻게 되는가?에 따라서 맞춰서 작업할 준비
    - 인피니트 스크롤
    - 탭전환
        - 각 탭에 맞는 정보들이 나오게 해야 한다.
    - 검색
    - 필터
    - 프로필
    - 게시하기(Create)
    - 반응형
- npx create-next-app으로 프로젝트 생성하기
    - public → 모두가 접근가능한 이미지 제공
    - src → app을 이 안에 둘 수 있다. app은 주소와 관련된 파일만 들어간다.
    - next.config.js → Next에 대한 설정파일
    - tsconfig.json → Typescript에 대한 설정파일(기본적인 내용만 사용 예정)
    - @/app/layout처럼 절대경로 사용가능한 옵션이 생성때 지정한 alias 속성
    - pakage.json에서 프로젝트 구동 script 확인하기.

## 브라우저 주소 app 폴더에 반영하기 & 라우트 그룹

- 페이지를 넘나들어도 바뀌지 않는 부분이 layout(RootLayout) → children으로 각 페이지에 대한 정보를 보여줌
- Singup, Signin 화면에서는 layout이 다름을 확인하고 적용해야 함
- 주소별 폴더 구조 확인하기
- app
    - (afterLogin) → 주소창에 관여하지 않지만, 그룹별로 묶을 수 있음
        - compose
            - tweet
                - page.tsx
        - [username] → 대괄호로 넣게 되면 username에 대응되는 각각의 폴더를 만들필요 없이 활용 가능(같은 디렉토리 선상에 있는 explore, home, messgaes, i, search를 username으로 못쓰게 해야함.
            - status
                - [id]
                    - page.tsx
            - page.tsx
        - explore
            - page.tsx
        - home
            - layout.tsx → RootLayout → HomeLayout → Home(page.tsx) 이렇게 렌더링이 이루어진다.
            - page.tsx
        - messages
            - page.tsx
            - zeroch0
                - page.tsx
        - search
            - page.tsx
        - layout.tsx → RootLayout과 HomeLayout 사이의 layout
    - (beforeLogin)
        - i
            - flow
                - signup
                    - page.tsx
                - login
                    - page.tsx
        - login
            - page.tsx → 리렌더링 시켜주는 컴포넌트
- not-found.tsx → 매칭 안되는 페이지 렌더링 시킬 파일

## template.tsx, Link, Image, redirect

- 페이지를 자주 넘나들지만, layout은 리렌더링이 되지 않도록 하는데 리렌더링을 되게 하고 싶으면 layout.tsx가 아니라 template.tsx를 사용해야 한다. → 기록을 해야되는 상황 같은 (Google Analytics) 것에 사용.
- next에서는 a태그가 아닌 Link 사용(새로고침이 안되도록 방지)
- 로그인은 twitter/login으로 간다고 되어 있는데, i/flow/login으로 가게 된다.
    - login 폴더에 page.tsx에 i/flow/login으로 리다이렉트(next/navigation redirect) 되도록 해놓음
- img → Image 사용(Next에서 최적화 해준다.)

## css module을 선택한 이유

- css는 간단하게 하기 위해서
    - tailwind → 호불호 너무 심하고 가독성이 좋지 않다.
    - Styled Component or Emotion → Server Component에서 취약
    - sass
    - css module → sass보다 간단함
    - vanilla extract → Windows와 문제가 생긴다
- 특정 페이지나 레이아웃에 적용할 부분을 page.module.css로 관리
- dvw, dvh → 모바일 주소창으로 문제가 생기는 부분에 맞춰서 전체화면을 맞춰주는 새로운 단위

## 페러렐 라우트

- 로그인을 눌렀을 때 뒤에 원래 홈화면은 남아있고 모달이 떠야함
- 최상위 page.tsx와 login안의 page.tsx를 동시에 띄울 수 있게 해주는 것
- (beforeLogin)
    - @modal → 이런식으로 추가한 후 pararel route를 하게 되면 문제가 발생한다. 왜냐하면 @modal 디렉토리와 최상위 page.tsx의 디렉토리 레벨이 다르기 때문. 그럴경우 최상위 page.tsx 파일을 @modal 디렉토리와 같은 선상으로 가져와야 pararel route가 가능하다.
        - page.tsx
    - page.tsx
    - layout.tsx → 병렬을 위한 layout 파일. @가 붙어있는 modal을 props로 받아 렌더링을 해준다.
- children → 매개변수 구조분해 할당한 부분이고 컴포넌트를 받아오기 때문에 ReactNode라는 타입을 할당해준다.

## 클라이언트 컴포넌트로 전환하기

- “use client”
    - useState는 CSR에서만 동작하는데 SSR에서 사용한다는 문제가 발생하는데 이는 해당 컴포넌트가 서버 컴포넌트로 지정되어 있기 때문이다.(Next 13버전부터 컴포넌트는 기본적으로 서버 컴포넌트다.) 이를 해결하기 위해 서버 컴포넌트로 해당 컴포넌트를 지정해줘야 하는데, 이 때 컴포넌트 최상단에 추가해줘야할 문장이 “use client”다.
    - **서버 컴포넌트의 장점과 클라이언트 컴포넌트의 필요성 사이에서 잘 선택하여 사용하여야 한다.**

## default.tsx

- 캐싱이 잘못되어 에러가 발생할 수 있어 확인해보기
- 우리는 그냥 /login에서 해당 모달이 뜨는 것이 아니라, i/flow/login에서 모달을 띄워야 하는데, 이 때 단순하게 디렉토리를 @modal 폴더 안에 만들어준다고 해결되는 것이 아니다. → 같은 선상에 있어야 pararel route가 되므로!
- pararel 라우트에 대한 기본값을 나타내는 파일이 default.tsx 이다.
- 주소가 [localhost:3000](http://localhost:3000) 일 때는 → children → page.tsx, modal → @modal/default.tsx
- 주소가 [localhost:3001/i/flow/login](http://localhost:3001/i/flow/login) 일 때는 children → i/flow/login/page.tsx, modal → @modal/i/flow/login/page.tsx가 사용된다.
- 이렇게 진행하면 뒷 화면이 유지되지 않고 모달에 대한 부분만 나온다.

## 인터셉팅 라우트

- (beforeLogin)/layout.tsx 기준에서는 i폴더, login폴더, page.tsx는 children에서 렌더링 됨.
- (.)i 이런식으로 하면 현재 폴더에 있는 i가 상위 폴더의 i(브라우저 주소 기준)을 대체할 수 있게 된다.
- 중간에 끼어들어 주소를 가로채서 보여준다는 의미
- **클라이언트에서 라우팅 할때만 적용된다는 부분!**
- 기존에 있던 i 폴더에 해당하는 내용은 새로고침을 할 때 필요함(이때는 pararel route와 인터셉팅 라우트가 필요가 없으므로)

## private folder(_폴더)

- 공통이 되는 부분이 있으면 _component라는 디렉토리를 만들어 공통된 컴포넌트를 넣고 해당 부분을 page.tsx에서 import하여 사용할 수 있다. 디렉토리 이름이 주소창에 노출 되지 않는다.
- 클라이언트가 서버 컴포넌트를 import하면 import한 컴포넌트가 클라이언트 컴포넌트로 바뀌고 서버가 import할 경우 그 역이 된다.
- 원칙적으로 서버 컴포넌트가 클라이언트 컴포넌트를 import해야 한다.

## 로그인 모달에서 발생하는 문제 해결하기(router.replace)

- css module은 실제 클래스명에 렌덤한 문자와 숫자를 추가해 클래스 이름이 겹치지 않도록 해준다.
- redirect → 서버에서 redirect 하게 되면 인터셉팅이 제대로 되지 않는 문제. 처음에는 해당 리다이렉트를 클라이언트 컴포넌트로 변경하지만 redirect는 서버 컴포넌트에서 더 유용하기에 변경할 예정.
- 클라이언트 에서는 router.replace 사용!
- router.push
    - [localhost:3001](http://localhost:3001) → [lcoalhost:3001/login](http://localhost:3001/login) → [localhost:3001/i/flow/login](http://localhost:3001/i/flow/login) → localhost:3001/login
- router.replace
    - [localhost:3001](http://localhost:3001) → http://localhost:3001/login → [localhost:3001/i/flow/login](http://localhost:3001/i/flow/login) → localhost:3001
- replace는 히스토리를 삭제해서 [localhost:3001/login의](http://localhost:3001/login의) 히스토리를 배제한다.
- Login 컴포넌트의 배경을 page.tsx와 같게 해줘야 동시에 보여진다. _component로 분리 추천
- 모달이 여러개면 @modal2, modal3 등 늘려서 렌더링 시켜줘야 한다.

## Main, SignupModal css 설명

- Main.tsx → 로그인 전 같은 레이아웃을 렌더링 시켜줄 메인 레이아웃
- 해당 css의 경우 직접 실습 및 클론 코드를 통한 학습을 진행했습니다.
- 전체적으로 display:flex 속성을 왜 부여했고 justify-content, align-items 의 속성을 부여했을 때 화면이 어떻게 나오는지 그리고 각 css가 해당 디자인에 맞게 적용이 되어 있음을 적용해제 및 적용으로 비교해서 알려주셨습니다.