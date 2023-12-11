# MobileAppTesting
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
