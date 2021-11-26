# react-native-initial
![](https://build.appcenter.ms/v0.1/apps/d6afaabd-26d3-460e-9828-fddee9707df2/branches/main/badge)
## IOS
1. Add the SDK to the project
In a terminal window opened at the root of a React Native project, enter the following line to add Crash and Analytics services to your app:
    ```
    npm install appcenter appcenter-analytics appcenter-crashes --save-exact
    ```
2. Integrate the SDK

    **2.1 install CocoaPods dependencies:**
   > IOS directory 
    ```
    pod install
    ```
    2.2 Create a new file with the name **AppCenter-Config.plist**
    > ../ProjectName/ios/Appcenter-Config.plist
    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "https://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
        <dict>
        <key>AppSecret</key>
        <string>3b31fd46-92fa-4a5f-bf2e-7c23b165ad6f</string>
        </dict>
    </plist>
    ```
    2.3 Modify the app's **AppDelegate.m** file to include code for starting SDK:
    > ../ProjectName/ios/ProjectName/AppDelegate.m
    ```
    #import <AppCenterReactNative.h>
    #import <AppCenterReactNativeAnalytics.h>
    #import <AppCenterReactNativeCrashes.h>
    ```
    2.4 Add these lines to the didFinishLaunchingWithOptions method
    ```
    [AppCenterReactNative register];
    [AppCenterReactNativeAnalytics registerWithInitiallyEnabled:true];
    [AppCenterReactNativeCrashes registerWithAutomaticProcessing];
    ```
3. Explore data

    Now build and launch your app, then go to the Analytics section. You should see one active user and at least one session! The charts will get more relevant as you get more users. Once your app actually crashes, you will have Crashes data show up as well.

## References
[App Center Sample App for React Native](https://github.com/microsoft/appcenter-sampleapp-react-native)

[React Native Tutorial #16 - Appcenter iOS Build Configuration and AppStore Submission | Tek Hub](https://www.youtube.com/watch?v=Xlpq8qv_8bI)