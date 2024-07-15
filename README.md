# AndriodExample
## Necessary Setups
### AndroidManifest.xml
Add permission at the top
```
<uses-permission android:name="android.permission.INTERNET"/>
```

Allow clear text traffic
In application tag add the following attribute
```
android:usesCleartextTraffic="true"
```

### activity_main2.xml
add web view controller
```
<WebView
        android:id="@+id/webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:visibility="gone"/>

```

Modify Main2Actiavity.java
add member variable
```
private WebView webView;
```

initialize the member variable in OnCreate Function
```
        webView = findViewById(R.id.webview);
        webView.setWebViewClient(new WebViewClient()); // 防止跳转到外部浏览器
        webView.getSettings().setJavaScriptEnabled(true); // 启用JavaScript
```


modify onClick
```
                webView.setVisibility(View.VISIBLE); // 显示WebView
                webView.loadUrl("http://www.google.com"); // 加载指定网页
```
