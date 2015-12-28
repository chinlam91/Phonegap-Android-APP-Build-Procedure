#Procedure of phonegap(android) app build release mode and upload to Google Playstore

###Use command line to package your code as release mode. Here is the sample for using cordova .
    
    ＄cordova build --release android
###Signing Your App Manually
  - Using keytool to generate your key

    ```$ keytool -genkey -v keystore publish.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000```
  
     _Hint: You can change your own keystore name , and the alias name. Don't forget your alias name and password_
  
  - Sign your app (.apk you created at the first step) with the key
  
    ```$ jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-publish.keystore my_application.apk alias_name```
    
  - Check your APK . If the apk is signed , the console will show "signed"
    
    ```$ jarsigner -verfiy -verbose -certs my_application.apk```
    
  - Zip your final apk 
  
    ```$ zipalign -v 4 your_application.apk xxx.apk``` 
    
    _Hint: You can rename the xxx.apk._
    

###Source
[Android Developer](developer.android.com/intl/zh-tw/tools/publishing/app-signing.html)

[Phonegap](https://cordova.apache.org)
