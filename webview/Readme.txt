activitymain xml
 -Change layout constarintlayout to linear layout layout
 -delete text view
 -delete    xmlns:app="http://schemas.android.com/apk/res-auto" in 2 nd line

 - goto design mode
 - drag and drop webview
 - add android ID to webview

 Main activity .java
 - declare webview
 - import webview

 add these

         web=findViewById(R.id.webview);
         WebSettings webSettings =web.getSettings();
         webSettings.setJavaScriptEnabled(true);
         web.setWebViewClient(new Callback());------> create inner class (dont import callback)
         web.loadUrl(" link");
 -import websettings

In the private class callback write {shouldoverride keyevent}---> remove {private class Callback extends WebViewClient {
                                                                              }

 -now add return false


ANDROIDMANIFEST XML

- add internet permission
 <uses-permission android:name="andriod.permission.INTERNET"/>
 <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>

 NOW IN RES FOLDER GOTO XML right click select new --> xml resource file  --> Filename=network_security_config

-remove prefernece screen complete tag
-add <network-security-config>

    <base-config cleartextTrafficPermitted="true"/>
     </network-security-config>

GOTO ANDROID MANIFEST

Under application tag add
        android:networkSecurityConfig="@xml/network_security_config"
