# [react-native] 기본 환경 셋팅

> 맥북에서 react-native 환경 설치하기
>
> homebrew, xcode는 이미 설치된 상태에서 시작



## 1. install nvm

> node version manager

- `homebrew` 로 설치

```bash
brew install nvm
```

- 설치 후 nvm 확인해보면 다음과 같이 뜸

```bash
zsh: command not found: nvm
```

- `.zshrc` 파일 vi로 수정

```bash
vi ~/.zshrc
```

- 아래와 같이 입력 후 `esc` +  `:wq` 입력하여 저장 후 종료

```bash
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh
```

- 적용시키기

```bash
source ~/.zshrc
```



## 2. install node

- nvm 이용해서 설치

```bash
nvm install node
```

- homebrew 이용해서 설치

```bash
brew install node
```



## 3. install watchman

> 특정 폴더나 파일을 감시하다 변화가 생기면 특정 동작 실행하도록 설정
>
> react-native에서 소스코드의 추가나 변경이 발생하면 다시 빌드하기 위해 사용

- homebrew 이용해서 설치

```bash
brew install watchman
```



## 4. install react native CLI

> 직접 native 어플리케이션 개발

- npm 명령어 통해 설치

```bash
npm install -g react-native-cli
```



## 5. install cocoapods

> iOS 개발에서 사용되는 의존성 관리자

- 코코아팟 설치

```bash
sudo gem install cocoapods
```



## 6. react-native 프로젝트 생성

- react-native CLI 명령어 통해 프로젝트 생성

```bash
react-native init AppName # 프로젝트 이름
```

- 실행

```bash
cd AppName
react-native run-ios # 또는 npm run ios
```

- 프로젝트 내부의 /ios 경로로 이동해 iOS 앱 개발에 필요한 라이브러리 설치

```bash
pod install
```



## 7. 기타 오류

- 다음과 같은 오류 발생

```bash
The iOS Simulator deployment targets is set to 7.0, but the range of supported deployment target version for this platform is 8.0 to 12.1
```

- `podfile` 의 맨 아래에 있는 부분 수정 및 추가

```bash
  post_install do |installer|
    installer.pods_project.targets.each do |target|
      target.build_configurations.each do |config|
        config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '9.0'
      end
    end
  end
```

- 링크
  - [s1](https://stackoverflow.com/questions/54704207/the-ios-simulator-deployment-targets-is-set-to-7-0-but-the-range-of-supported-d)
  - [s2](https://stackoverflow.com/questions/63056454/xcode-12-deployment-target-warnings-when-using-cocoapods)

