### React-Native

#### environment setup MacOS + ios(xcode)
1. requirement
- node version over 12
- nvm version over 6
- Simulator(xcode)

2. init project
exoi-cli 전역설치
```
npm install -g expo-cli
```
프로젝트 생성
```
expo init AwesomeProject

cd AwesomeProject
```

#### environment setup MacOS + android
1. node & watchman
```
brew install node
brew install watchman
```

2. java development kit
```
brew cask install adoptopenjdk/openjdk/adoptopenjdk8
```

3. android development environment
   - Install Android Studio
      1. Android SDK
      2. Android SDK Platform
      3. Android Virtual Device
      4. If you are not already using Hyper-V: Performance (Intel ® HAXM) (See here for AMD or Hyper-V)
   - Install the Android SDK
     - Android Studio installs the latest Android SDK by default. Building a React Native app with native code, however, requires the Android 10 (Q) SDK in particular. Additional   
       Android SDKs can be installed through the SDK Manager in Android Studio. To do that, open Android Studio, click on "Configure" button and select "SDK Manager".
   - Configure the ANDROID_HOME environment variable

   * edit .bash_profile
     - $cd ~
     - $vim .bash_profile
     - copy below code
     - $source .bash_profile
```
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

4. creating a new application
```
npx react-native init AwesomeTSProject --template react-native-template-typescript
cd AwesomeTSProject
```

5. Running your React Native application
```
npx react-native run-android
```