-> Edit Group Policy -> **_Computer Configuration -> Administrative Templates -> Windows Components -> Windows Updates ->_**

		->**_Configure Automatic Updates_** _->_ Enable the policy and select the following "Configure automatic updating" in the "Options" section:
- _Auto download and notify for install_

		->**_Specify intranet Microsoft update service_** _->_ Enable the policy and set both URL’s in the "Options" section:
 [_http://Your_WSUS_Server_Hostname:8530_](http://wsusserverip:8530/) 
    - Note: if [using SSL](https://kc.jetpatch.com/hc/en-us/articles/360043618872-Enabling-SSL-on-WSUS-) use **https** and **8531**
    - http://10.124.9.98:8530

		-> - **_Automatic Update detection frequency_** _->_ Enable the policy and set "Check for updates at the following interval (hours)" in the "Options" section:
    - _4 hours_

		->- **_Allow signed updates from an intranet Microsoft update service location_** _->_ Enable the policy
    - **This is required** in order to install non-Microsoft [3rd Party Software Updates](https://kc.jetpatch.com/hc/en-us/articles/360054473392-3rd-Party-Software-Solution-Overview) and when [SSL](https://kc.jetpatch.com/hc/en-us/articles/360043618872-Enabling-SSL-on-WSUS-) has been configured on the WSUS server.


		->- Enable the execution policy by going to **_Computer Configuration -> Administrative Templates -> Windows Components -> Windows PowerShell_** _->_
    - _**Turn on Script Execution** -> Enable the policy and set "Allow local scripts and remote signed scripts" in the "Options" section_



_**Optional Policy**_

- Restrict users not to pause the updates in the endpoints enable this policy.
    - _**Computer Configuration -> Administrative Templates -> Windows Components -> Windows Updates ->**_ _**Remove Access to "Pause updates" feature** -> Enable the Policy._
- now linux
etgswghgfesg



# Start building Flutter Android apps on Windows

1. [Get started](https://docs.flutter.dev/get-started)
2. [Install](https://docs.flutter.dev/get-started/install)
3. [Windows](https://docs.flutter.dev/get-started/install/windows)
4. [Make Android apps](https://docs.flutter.dev/get-started/install/windows/mobile)

## Software requirements

To write and compile Flutter code for Android, you must have the following version of Windows and the listed software packages.

### Operating system

Flutter supports developing on 64-bit versions of Windows 10 and 11.

### Development tools

Download and install the Windows version of the following packages:

- [Git for Windows](https://gitforwindows.org/) to manage Flutter versions and your own source code versioning.
    
- [Android Studio](https://developer.android.com/studio/install#windows) to debug and compile Java or Kotlin code for Android.
    

The developers of the preceding software provide support for those products. To troubleshoot installation issues, consult that product's documentation.

## Configure a text editor or IDE

You can build apps with Flutter using any text editor or integrated development environment (IDE) combined with Flutter's command-line tools.

Using an IDE with a Flutter extension or plugin provides code completion, syntax highlighting, widget editing assists, debugging, and other features.

Popular options include:

- [Visual Studio Code](https://code.visualstudio.com/docs/setup/windows) with the [Flutter extension for VS Code](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter).
- [Android Studio](https://developer.android.com/studio/install#windows) with the [Flutter plugin for IntelliJ](https://plugins.jetbrains.com/plugin/9212-flutter).
- [IntelliJ IDEA](https://www.jetbrains.com/help/idea/installation-guide.html) with the [Flutter plugin for IntelliJ](https://plugins.jetbrains.com/plugin/9212-flutter).

Recommended

The Flutter team recommends installing [Visual Studio Code](https://code.visualstudio.com/docs/setup/windows) and the [Flutter extension for VS Code](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter). This combination simplifies installing the Flutter SDK.

## Install the Flutter SDK

To install the Flutter SDK, you can use the VS Code Flutter extension or download and install the Flutter bundle yourself.

### Use VS Code to install Flutter

To install Flutter using these instructions, verify that you've installed [Visual Studio Code](https://code.visualstudio.com/docs/setup/windows) and the [Flutter extension for VS Code](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter).

#### Prompt VS Code to install Flutter

1. Launch VS Code.
    
2. To open the **Command Palette**, press Control + Shift + P.
    
3. In the **Command Palette**, type `flutter`.
    
4. Select **Flutter: New Project**.
    
5. VS Code prompts you to locate the Flutter SDK on your computer.
    
    1. If you have the Flutter SDK installed, click **Locate SDK**.
        
    2. If you don't have the Flutter SDK installed, click **Download SDK**.
        
        This option sends you the Flutter install page if you haven't installed Git for Windows as directed in the [development tools prerequisites](https://docs.flutter.dev/get-started/install/windows/mobile#development-tools).
        
6. When prompted **Which Flutter template?**, ignore it. Press Esc. You can create a test project after checking your development setup.
    

#### Download the Flutter SDK

1. When the **Select Folder for Flutter SDK** dialog displays, choose where you want to install Flutter.
    
    VS Code places you in your user profile to start. Choose a different location.
    
    Consider `%USERPROFILE%` or `C:\dev`.
    
    Warning
    
    Don't install Flutter to a directory or path that meets one or both of the following conditions:
    
    - The path contains special characters or spaces.
    - The path requires elevated privileges.
    
    As an example, `C:\Program Files` meets both conditions.
    
2. Click **Clone Flutter**.
    
    While downloading Flutter, VS Code displays these pop-up notifications:
    
    ```
    Downloading the Flutter SDK. This may take a few minutes.
    ```
    
    content_copy
    
    ```
    Initializing the Flutter SDK. This may take a few minutes.
    ```
    
    content_copy
    
    The download and installation take a few minutes. If you suspect that the download has hung, click **Cancel**, then start the installation again.
    
    When the Flutter installation succeeds, VS Code displays this pop-up notification:
    
    ```
    Do you want to add the Flutter SDK to PATH so it's accessible
    in external terminals?
    ```
    
    content_copy
    
3. Click **Add SDK to PATH**.
    
    When successful, a notification displays:
    
    ```
    The Flutter SDK was added to your PATH
    ```
    
    content_copy
    
4. VS Code might display a Google Analytics notice.
    
    If you agree, click **OK**.
    
5. To enable `flutter` in all PowerShell windows:
    
    1. Close, then reopen all PowerShell windows.
    2. Restart VS Code.

## Configure Android development

### Configure the Android toolchain in Android Studio

[Help](https://docs.flutter.dev/install/troubleshoot#android-setup "Troubleshoot common installation issues")

To create Android apps with Flutter, verify that the following Android components have been installed.

- **Android SDK Platform, API 35**
- **Android SDK Command-line Tools**
- **Android SDK Build-Tools**
- **Android SDK Platform-Tools**
- **Android Emulator**

If you haven't installed these, or you don't know, continue with the following procedure.

Otherwise, you can skip to the [next section](https://docs.flutter.dev/get-started/install/windows/mobile#check-your-development-setup).

1. Launch **Android Studio**.
    
    The **Welcome to Android Studio** dialog displays.
    
2. Follow the **Android Studio Setup Wizard**.
    
3. Install the following components:
    
    - **Android SDK Platform, API 35**
    - **Android SDK Command-line Tools**
    - **Android SDK Build-Tools**
    - **Android SDK Platform-Tools**
    - **Android Emulator**

### Configure your target Android device

#### Set up the Android emulator

[Help](https://docs.flutter.dev/install/troubleshoot#android-setup "Troubleshoot common installation issues")

To configure your Flutter app to run in an Android emulator, follow these steps to create and select an emulator.

1. Enable [VM acceleration](https://developer.android.com/studio/run/emulator-acceleration#accel-vm) on your development computer.
    
2. Start **Android Studio**.
    
3. Go to the **Settings** dialog to view the **SDK Manager**.