# TitleBar
# 安装
**Step 1**:Add it in your root build.gradle at the end of repositories     

```
	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
 ```
 **Step 2**:Add the dependency
 ```
 	dependencies {
 	        compile 'com.github.MarshallMathersIII:TitleBar:v1.0'
 	}
```
# 使用
**Step 1**:自定义布局
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/rl_titlebar"
    android:layout_width="match_parent"
    android:layout_height="?attr/actionBarSize"
    android:background="@color/white"
    android:orientation="horizontal" >

    <ImageView
        android:id="@+id/titlebar_iv_left"
        android:layout_width="48dp"
        android:layout_height="match_parent"
        android:layout_centerVertical="true"
        android:padding="12dp"
        android:visibility="gone" />

    <TextView
        android:id="@+id/titlebar_tv_left"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:gravity="center_vertical"
        android:paddingLeft="16dp"
        android:paddingRight="16dp"
        android:textColor="@color/txt_black"
        android:textSize="@dimen/txtsize_subhead"
        android:visibility="gone" />

    <TextView
        android:id="@+id/titlebar_tv"
        style="@style/TextViewTitle"
        android:layout_centerInParent="true"
        android:gravity="center"
        android:maxWidth="224dp" />

    <ImageView
        android:id="@+id/titlebar_iv_right"
        android:layout_width="48dp"
        android:layout_height="match_parent"
        android:layout_alignParentRight="true"
        android:layout_centerVertical="true"
        android:padding="12dp"
        android:visibility="gone" />

    <TextView
        android:id="@+id/titlebar_tv_right"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_alignParentRight="true"
        android:gravity="center_vertical"
        android:paddingLeft="16dp"
        android:paddingRight="16dp"
        android:textColor="@color/txt_black"
        android:textSize="@dimen/txtsize_subhead"
        android:visibility="gone" />

    <View
        android:layout_width="match_parent"
        android:layout_height="1px"
        android:layout_alignParentBottom="true"
        android:background="@color/bg_agray" />

</RelativeLayout>
```
**Step 2**:使用
```
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        new TitleBuilder(this)
                .setTitleText("设置")
                .setLeftImage(R.mipmap.ic_launcher)
                .setLeftOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        finish();
                    }
                });
    }
}
```

