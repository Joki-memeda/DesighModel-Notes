# Content Provider(内容提供器)

* 主要应用于在不通的应用程序间的实现数据共享的功能

## 运行时权限
* [查看完整权限列表](https://developer.android.com/reference/android/Manifest.permission.html)
#### 权限的申请
在AndroidManifest.xml文件声明即可：
```xml
<uses.permission android:name="android.permission.CALL_PHONE"/>
```

## 访问其他程序中的数据
### ContentReslover的基本用法
* ContentReslover中提供了一系列的方法用于对数据进行CRUD操作
    * insert() 添加
    * update() 更新
    * delete() 删除
    * query() 查询

* ContentResolover中的增删改查方法都是使用一个Uri参数代替，这个参数被称为内容URI。
    
    * 内容URI由两部分组成 标准写法 `content://com.example.app.provider/table`
        
        * authority 对不同的应用程序做区分 `com.example.app.provider`
        
        * path 对同一个应用程序中的不同的表作区分,一般添加在authority后面 `com.example.app.provider/table`
        
`把内容URI解析为Uri对象： Uri uri = Uri.parse("content://com.example.app.provider/table");`
