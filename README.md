# AndroidCompatProblem
Android开发兼容性问题汇总

---
## 5.0以下`drawable`不支持`?`或`?attr`引用颜色属性的值
#### 问题
创建drawable.xml时，不支持`?`或`?attr`引用颜色属性的值。(`vector`中的`path`标签可采用`?attr`)

#### 解决
将`?`或`?attr/`引用方式改成`@android:color/`或`@color/`

---
## 采用 DownloadManager 实现应用下载更新时，下载完成后点击通知部分设备提示`格式错误`或`无法打开此文件`
#### 解决
明确指定下载目录

---
## 5.0以下`vector`采用`@color`设置颜色无效
#### 问题
```xml
<vector xmlns:android="http://schemas.android.com/apk/res/android"
        android:width="24dp"
        android:height="24dp"
        android:viewportWidth="24.0"
        android:viewportHeight="24.0">
    <path
        android:fillColor="@android:color/white"
        android:pathData="......"/>
</vector>
```
`android:fillColor="@android:color/white"`这种设置颜色时5.0以下无效

#### 解决
方案一：升级 support 版本到26以上，检查自己的 support 版本是不是25或更低
方案二：不采用引用颜色值的方式设置，直接设置相应的颜色值，如`android:fillColor="#FFFFFFFF"`
