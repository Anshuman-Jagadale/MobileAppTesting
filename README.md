# iOS Mobile App Testing
Contents of this Guide
## Prerequisites
* Xcode
* Xcode Command Line Tools
* Homebrew
* Carthage
* asdf
## Android Studio Setup
* Java 8 JDK
* JAVA_HOME
* ANDROID_HOME
* Android Emulator
## iOS Setup
* iOS Simulator
## Appium
* Node.js
* Appium Server
* Appium Desktop

### Install Appium 

1. Explanation link: https://medium.com/tauk-blog/quick-start-guide-for-setting-up-appium-on-an-m1-mac-a629a70a40cb
2. Homebrew:
   Homebrew is a popular package manager for macOS. It has an extensive collection of packages, which it calls formulae (CLI) and casks (GUI).
   To install Homebrew, you can execute their interactive installation script in your terminal:
   `\/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
4. Carthage:
   Carthage is a popular dependency manager for macOS and iOS projects. You can install it via homebrew:
   `brew install carthage`
   **Note**: The XCUITest driver for Appium previously required Carthage being installed. However, as of Appium 1.20.0+ it’s technically not required anymore. That said, it’s still helpful to have since some optional dependencies you may want to use do require Carthage.
5. asdf: asdf is a convenient version manager for language runtimes. It provides a single CLI tool you can use for installing Node, Java, and other languages. For those that have used nvm before, it’s like a generalized nvm, but inclusive of other languages.
   First install the requisite dependencies based on your platform. Then you can proceed to install it. For example using Homebrew on macOS:
   `brew install asdf`
* Install xcode, android studio
* Install npm `brew install node`
* Install java `brew install java` (or set specific version of JDK)
* Install Appium: 
  * `npm i --location=global appium`
  * associate appium filename: `sudo ln -fs /opt/homebrew/Cellar/node/21.1.0/lib/node_modules/appium/build/lib/main.js /usr/local/bin/appium` add permissions `chmod +x /usr/local/bin/appium`
  * check appium is installed `appium -v`

### Appium usage
* Check available drivers list `appium driver list`
* Install a driver `appium driver install xcuitest`
* Start an Appium `appium`

# Android Mobile App Testing
This project shows Appium and Serenity framework integration to run sample test case on native Android app.
## Required

1. Download [Java OpenJDK 11](https://jdk.java.net/java-se-ri/11)
   [Tutorial Installation Java in Windows](https://www.petanikode.com/java-windows/)
2. Download [Maven](https://maven.apache.org/download.cgi?Preferred=ftp://ftp.osuosl.org/pub/apache/)
3. Install [Appium](https://appium.io/docs/en/2.0/quickstart/install/)
5. Install [uiautomator2 driver](https://appium.io/docs/en/2.0/quickstart/uiauto2-driver/)
6. Set env variable JAVA PATH
7. Set env variable MAVEN PATH
8. Set env variable APPIUM PATH
9. Have a android device or emulator

`*If your computer already installed Java, Maven and Appium, you can skip all step.`
## This project run on
1. serenity 4 version
2. appium 2 version


## Setting Appium capabilities in serenity.properties
1. appium.hub = Appium server URL
2. appium.platformName = Fill with your android platform name
3. appium.platformVersion  =  Fill with your android platform version
4. appium.deviceName  =  Fill with name of your device
5. appium.app  =  App file path
   drop your apk file in directory path that has been provided `src/test/resources/apkFile`

## Setting Appium path location in application.properties
1. appium.driver.path = path of appium driver
2. appium.js.path = path of js file

## Download Code Editor IntelliJ IDEA Community Edition (Optional)
Download [IntelliJ IDEA](https://www.jetbrains.com/idea/download)

`*IntelliJ IDEA for your code editor is optional, you can still used another code editor like Eclipse or Visual Studio Code.`

## Added New Scenario BDD

In order to add some Scenario BDD, we can create new file feature in directory `src/test/resources/features`

## Writing the step definitions (Breaking Down Scenario BDD Into Steps)

In order to translate the steps from Scenario BDD into executable actions, we write Java classes called Step Definitions in directory `src/test/java/steps`

## Writing the Page Object Class

Page Objects are a way of isolating the implementation details of a web page inside a class, exposing only business-focused methods related to that page.
We can create new Page Object file in directory `src/test/java/pages`


## Running Test Case

```
mvn clean verify
```

## Running Test Cases with spesific device

```
mvn clean verify -Dproperties=android2.properties
```
## Running Test Cases with tags and spesific device

```
mvn clean verify -Dtags=invalidCredentials -Dproperties=android2.properties 
```
