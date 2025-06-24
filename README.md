Enable JavaScript

        WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);

Manage ProgressBar

      webView.setWebViewClient(new WebViewClient(){
            @Override
            public void onPageStarted(WebView view, String url, Bitmap favicon) {
                pBar.setVisibility(View.VISIBLE);
                super.onPageStarted(view, url, favicon);
            }

            @Override
            public void onPageFinished(WebView view, String url) {
                pBar.setVisibility(View.GONE);
                super.onPageFinished(view, url);
            }
        });

Manage Stack

    public void onBackPressed() {

        if(webView.canGoBack())
            webView.goBack();
        else
            super.onBackPressed();
    }

    <ProgressBar
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/pBar"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        android:visibility="gone"/>
