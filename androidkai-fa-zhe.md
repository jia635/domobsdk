如果运行如果运行项目的targetSdkVersion是23，安卓系统为6.0及以上系统则需要动态申请READ_PHONE_STATE和WRITE_EXTERNAL_STORAGE权限，申请过程如下：
（1）设置申请权限的监听，监听用户授予权限的状态
						DOW.getPermissonHelper(this).setOnApplyPermissionListener(new OnGainPermissionListener() {
				//所有权限都成功申请
				@Override
				public void onAllPermissionGained() {
					
				}
				 //用户拒绝了某一个权限，pair.first:权限名称 ；pair.second:权限描述
				@Override
				public void onRefuse(Pair<String, String> permission_msg) {

				}
				//用户勾选了不再显示
				@Override
				public void onRefuseForever() {
					
				}
				//最终授权失败
				@Override
				public void onGainedFail() {
					
				}
			}); 

	（2）申请权限

			DOW.getPermissonHelper(this).applyPermissions();

	 (3)在activity中重新onRequestPermissionsResult方法，在此方法中调用多盟权限帮助类相关方法
			@Override
			public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {
				super.onRequestPermissionsResult(requestCode, permissions, grantResults);
				//调用多盟权限帮助类相关方法
				DOW.getPermissonHelper(this).onRequestPermissionsResult(requestCode,permissions,grantResults);
			}

如果运行项目的targetSdkVersion是24即安卓7.0则需要做以下适配
在AndroidManifest注册provider
<!--兼容7.0 文件共享-->
        <provider
            android:name="android.support.v4.content.FileProvider"
            android:authorities="包名.fileProvider"
            android:exported="false"
            android:grantUriPermissions="true">
            <!--我们提供 file_paths，也可以在demo中 res/xml下找到-->
            <meta-data
                android:name="android.support.FILE_PROVIDER_PATHS"
                android:resource="@xml/file_paths" />
        </provider>
        