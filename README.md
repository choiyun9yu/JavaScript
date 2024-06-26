# JavaScript

## 1. Node.js
Node.js는 JavaScript를 브라우저 밖에서도 사용할 수 있게 해주는 JavaScript 실행 환경이다.

## 2.npm(Node Package Manager)
npm은 Node.js 패키지 관리자로, JavaScript 패키지 및 라이브러리르 설치, 업데이트 및 관리하는데 사용된다.  

package.json 파일에 프로젝트 정보와 종속성을 정의한다.

    # npm 특정버전 업그레이드
    % sudo npm install -g npm@x.x.x

    % npm init                  // package.json 생성
    % npm install {라이브러리}     // 특정 라이브러리 설치 (package.json 자동 업데이트)
    % npm install package.json  // package.json으로 의존성 일괄 설치


### 2-1. n으로 npm 버전 관리하기
    % npm install -g n  // n 설치

    % sudo n stable     // 안정 버전 설치
       n latest         // 최신 버전 설치
       n lts            // lts 버전 설치
       n x.x.x          // 특정 버전 설치 ( x.x.x 버전 )

    % n ls              // 설치 목록 보기
    % sudo n            // 방향키로 버전 선택 후 엔터
    % n rm x.x.x        // 특정 버전 삭제

### 2-2. npx
npx는 npm 패키지 실행 도구이다. 특히 CLI도구나 일회성 스크립트를 실행할 때 유용하다. npm 패키지를 전역으로 설치하지 않고, 필요할 때 실행할 수 있도록 도와준다.

### 2-3. yarn
npm과 비슷한 역할을 하는 패키지 관리자이다. yarn은 yarn.lock 파일을 사용하여 프로젝트 패키지 의존성을 관리한다.

    # 설치
    % sudo npm install -g yarn
    % yarn --version
    % export PATH="$PATH:/opt/yarn-[version]/bin"

    # 사용법
    % yarn init     // 프로젝트 시작 시 초기화 하려면 (package.json 생성)
    % yarn install  // package.json 으로부터 의존성 모듈 설치

    # 의존성 모듈 설치
    % yarn add [package]    // yarn.lock, package.json에 자동으로 반영
    % yarn add [package]@[version]
    % yarn add [package]@[tag]

    # 의존성 모듈 업그레이드
    $ yarn upgrade [package]
    $ yarn upgrade [package]@[version]
    $ yarn upgrade [package]@[tag]

    # 의존성 모듈 제거
    % yarn remove [package]

## 3. Dependency

    # 의존성 관련 node 모듈 삭제 후 다시 설치
    % rm -rf yarn.lock
    % rm -rf node_modules/
    % yarn

### 4. ERROR

#### 3-1. Watchpack Error (watcher)
> Error: ENOSPC: System limit for number of file watchers reached ...

    sudo sysctl -w fs.inotify.max_user_watches=524288    
