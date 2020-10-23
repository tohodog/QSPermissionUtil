# QSPermissionUtil
Android Permission Util 安卓权限申请工具类
## Copy and paste just do it! 复制粘贴就是干!
```
    PermissionUtil.requestPermission(this, new PermissionUtil.PermissionListener() {
        @Override
        public void onPermissionSucceed(int requestCode, List<String> grantedList) {
        
        }

        @Override
        public void onPermissionFailed(int requestCode, List<String> deniedList) {
            if (QSPermissionUtil.isAlwaysDeniedPermission(MainActivity.this, deniedList)) {
                QSPermissionUtil.showSettingDialog(MainActivity.this);
            }
        }
    }, PermissionUtil.SDCARD);
```
## API
```
  requestPermission() 申请权限,带回调
  requestRationalePermission() 被拒一次后会先弹出提示框,再申请权限
  hasPermission() 判断权限
  isRationalePermission() 是否被拒绝了一次了
  isAlwaysDeniedPermission() 是否永远拒绝了,需要在onPermissionFailed里调用,再弹出系统设置框showSettingDialog()
```
