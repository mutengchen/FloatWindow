# FloatWindow
android 悬浮按钮控件（可全屏拖动）

引用
```
    implementation 'com.github.mutengchen:FloatWindow:0.4'
```
权限申请
```
<uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"></uses-permission>
```
需要去打开悬浮窗设置才能使用
```
Intent permessionIntent = new Intent("android.settings.action.MANAGE_OVERLAY_PERMISSION", Uri.parse("package:" + context.getPackageName()));
                            startActivityForResult(permessionIntent, 100);


```
初始化控件
```
floatDialogWindow = FloatDialogWindow.getInstance(this);

//设置按钮的显示图片
floatDialogWindow.setBtnImg(R.drawable.go_button, new FloatDialogWindow.FloatWindowOnClickListener() {
            @Override
            public void onBtnClick() {
                //TODO 这里是触发点击事件之后，自己去实现
            }
        });
```

显示悬浮按钮
```
      //showWindow(width,height,x,y) width，height是按钮的宽高，x,y是按钮显示的位置，以左上角为原点
       floatDialogWindow.showWindow(60, 60, 0, 100);
```

隐藏悬浮按钮
```
      floatDialogWindow.hideWindow();
```
