# Mybrowser


            <intent-filter>

                <action android:name="android.intent.action.VIEW" />
                <category android:name="android.intent.category.DEFAULT" />

            </intent-filter>
            
        <WebView
        android:id="@+id/wbvw"
        android:layout_width="match_parent"
        android:layout_height="match_parent"></WebView>
        
        
         protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        WebView webView = (WebView)findViewById(R.id.wbvw);
        webView.getSettings().setJavaScriptEnabled(true);//让浏览器支持javascript
        webView.setWebViewClient(new WebViewClient());
        Intent intent=getIntent();
        Bundle bundle=intent.getExtras();
        if(bundle!=null) {
            String address=bundle.getString("address");
            webView.loadUrl(address);
        }

    }
