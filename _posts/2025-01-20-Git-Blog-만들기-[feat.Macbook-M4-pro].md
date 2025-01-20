# 1. 왜 Git 으로 블로그를 만들어?
서칭을 하다보면 다양한 블로그들이 있다. naver, tistory, velog 등등.

선택하게 된 이유는 상당히 단순하다. 그냥 가장 개발자의 냄새가 많이나고, Github와 연동이 되며(잔디심기 가능 ㅋㅋ) 마크다운 지원도 잘 되고, 마음대로 커스터마이징이 가능하다는 것 ?

But, 진입장벽이 굉장...히 높다. 쉽지 않습니다. 😱

네이버 블로그를 운영중이긴 하지만, 개발자는 네이버 검색보단 google검색을 많이 이용하기 때문에 기술블로그는 gitbub로 직접 만들어서 작성하기로 마음 먹었습니다.

첫 post를 보셨을지 모르겠지만.. 굉장히 시간을 잡아먹고 개설하게 됐습니다. 

혹시나 github 블로그 개설을 고민하는 분께 도움이 됐으면 하는 마음으로 개설과정 중 있었던 고난과 트러블슈팅을 했던것을 기록하며 가장 쉬운 방법으로 Github 블로그 개설이 가능한 일지를 작성하겠습니다!~ 😊

아 그리고 제가 Github 블로그를 생성할 때 사용했던 테마가 Jekyll Chirpy 테마 이기 때문에 (현재 제 블로그의 양식입니다. 대부분 분들이 이 양식을 쓰고 있어요.) 이 테마를 바탕으로 Github 블로그 생성일지를 작성 할 예정입니다.

(Mac 환경을 기준으로 작성됩니다.)

# 2. 로컬 환경 설정하기
### ruby 설치하기
- ruby 설치가 필수이기 때문에 아래 문서를 참고하여 ruby를 설치해줍니다.로컬에서 jekyll을 실행시켜 환경 설정이나 포스팅 결과를 미리 확인하기 위한 용도입니다.

- 참고 :  https://jekyllrb.com/docs/installation/

```zsh
$ brew update
$ brew install ruby
```

### chripy 테마 설치하기
1. [Github](https://github.com/cotes2020/jekyll-theme-chirpy) 에서 소스를 zip으로 받아 설치하기

    처음에 이 방법으로 시도를 했으나 배포를 하는 과정에서 여러 에러가 발생해서 결국 아래에 소개하는 방법을 사용해서 진행했습니다.
    fork로 할 때 보다 간편한 방법이긴 했지만 제 환경에서는 적절하게 적용되지 못했어요.😭
    
2. [Github](https://github.com/cotes2020/jekyll-theme-chirpy) 에서 소스를 fork 받아서 설치하기

    fork 받은 후 몇 가지 커스터마이징을 필수로 해주어야 합니다. 원하는대로 쉽게 커스터마이징이 가능하고 블로그를 커스터마이징 하겠다면 이 방법을 사용하는 것을 추천합니다!

저는 2번 방법을 통해 진행했기 때문에, 2번 설치법을 기준으로 작성합니다. 1번으로 설치를 희망하시는 분들은 조금만 구글링하시면 원하는 글을 금방 찾을 수 있을거에요!!

### Chirpy 테마 fork 하기
[Chirpy Fork](https://github.com/cotes2020/jekyll-theme-chirpy/fork) 링크로 들어가서 레퍼지토리를 fork 해옵니다.

이때, 레퍼지토리 이름을 **{github_user.name}.github.io** 양식과 같이 변경하여 아래 사진과 같이 설정해줍니다.
![Example Image](/assets/img/image1.png)

### 소스코드 클론 받기
GitHub 블로그를 제어 할 디렉토리 안에서 아래의 명령을 사용해 소스코드를 클론받는다.
```zsh
$ git clone (Git 레퍼지토리 url)
```

### Chirpy 초기화 하기
내려받은 레포지토리 디렉토리 안으로 이동하여 아래 명령어를 통해 chirpy를 초기화 합니다.
```zsh
$ tools/init.sh

Initialization successful! <-- 이런 메세지가 나오면 성공!!
```

위 명령어를 수행하면 기존 레퍼지토리에 커스터마이징 되어있던 내용들이 삭제된다. (fork를 받아 왔기 때문에 필요한 과정)

### 로컬에서 실행하기
jekyll을 로컬에서 실행하기 위해서는 의존성이 있는 모듈을 모두 설치해주어야 한다.
이미 chirpy에 기본으로 설정이 되어 있기때문에, 아래 명령어 만 입력하면 필요한 모든 것이 설치됩니다.
```zsh
$ bundle
```
설치가 완료되고 나면 다음 명령을 통해 jekyll을 실행시키면 됩니다.

```zsh
$ jekyll serve
```
정상적으로 수행됐다면 아래와 같이 출력이 됩니다.

![alt text](/assets/img/serverrun.png)

보시다시피 **Server address: http://127.0.0.1:4000/** 라고 떠있습니다.

브라우저를 열어 해당 주소를 입력해보면, 기본 블로그 화면이 나타납니다. 블로그 화면이 잘 나온다면 로컬에서의 테스트는 **성공**입니다 !!👏👏👏



# What's next
이렇게 해서 기본적인 레퍼지토리를 생성하고 로컬 환경을 설정한 뒤 테스트까지 마쳤습니다.

포스팅이 너무 길어지는 것 같아서, 다음 포스팅에 이어서 진행하겠습니다.

다음 포스팅에서는 Chirpy 환경설정과 첫 포스팅 작성 그리고 서버 배포하기(가능하다면) 까지 해보겠습니다.

읽어주셔서 감사합니다 !!😊😊


<br>

# 문제 해결
진행을 했을 때 몇가지 에러가 발생할 수 있습니다. <br>제가 겪었던 문제를 바탕으로 정리 해보겠습니다.

1. **command not found: jekyll**

    - 로컬 환경에 jekyll이 설치되지 않아서 그렇습니다.
    - [MacOS에 Jekyll](https://jekyllrb-ko.github.io/docs/installation/macos/) 설치를 참조하여 설치 해줍시다.

2.  HTML-Proofer found 2 failures!<br>
Error: Process completed with exit code 1.

    - 포스트를 작성하고 commit 후 push가 정상적으로 되었는데 배포에서 문제가 발생 했습니다.
    - 이미지를 넣고 작성하는 포스트가 처음이라 이미지를 저장할 디렉토리를 잘못 지정해서 발생한 에러였어요.
    - 이미지 경로를 /assets/img/ 폴더에 저장했더니 배포가 잘 됐습니다.


### 참고
    - https://www.irgroup.org/
    - https://sogummi.tistory.com/11
    