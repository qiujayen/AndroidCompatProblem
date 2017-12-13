# AndroidCompatProblem
Android开发兼容性问题汇总

## 5.0以下`drawable`不支持`?`或`?attr`引用颜色属性的值
#### 问题
创建drawable.xml时，不支持`?`或`?attr`引用颜色属性的值。(`vector`中的`path`标签可采用`?attr`)

#### 解决
将`?`或`?attr/`引用方式改成`@android:color/`或`@color/`
