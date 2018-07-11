
## 序
这是一个关于浏览器cookie，sessionStorage，localStorage操作的插件，它增加并完善了原有API功能。该插件包括[LsyCookie](http://blog.csdn.net/weixin_41424247/article/details/78859294), [LsySession](http://blog.csdn.net/weixin_41424247/article/details/78879326), [LsyStorage](http://blog.csdn.net/weixin_41424247/article/details/78872004) 三个部分，使用方法非常简单，直接引入[storages.js](https://github.com/loushengyue/storage-group/archive/master.zip)即可。

## vue-storages在vue开发环境下的使用方法

### 安装

```
$ npm install vue-storages --save
# OR
$ yarn add vue-storages
```
### 模块导入与配制

```
import Vue from 'vue'
import LsyStorages from 'lsy-storages'

Vue.use(LsyStorages, {
    localStorage: true
    sessionStorage: true,
    cookie: true
})
```

### demo

```
export default {
  name: "testPage",
  created(){
      this.$localStorage.setItem('greet', 'hello world.')
      this.$sessionStorage.setItem('name', 'loushengyue')
      this.$cookie.setItem('bye', 'just for test', 600000)
  }
};
```

### LsyCookie部分

主要方法有：

```
//cookie名称key，值val,过期时间time(单位s), path路径
this.$cookie.setItem(key[string], val[string|object], time[number], path[string])

//通过cookie名称获取
this.$cookie.getItem(key[string])

//获取所有cookie
this.$cookie.getAll()

//通过cookie名称删除, path为路径（默认为当前路径）
this.$cookie.removeItem(key[string], path[string:default('./')])

//删除所有cookie
this.$cookie.clear()
```


### LsySession部分

```
//设置sessionStorage信息，key为记录名称（字符串），value为字（可以是字符串或者对象）
this.$sessionStorage.setItem(key[string], value[string|object])

//设置sessionStorage信息，prex为记录前缀名（字符串），values为需要存储的信息集合（数组），byId表示是否以被存储对象的ID为后缀名或者说为下标（boolean)
this.$sessionStorage.setArr(prex[string], values[array], byId[boolean])

//通过数组与数组映射的方式存储信息，要求两数组长度相等，且keys内部元素为字符串类型
this.$sessionStorage.setList(keys[array], values[array])

//通过记录名称获取sessionStorage信息
this.$sessionStorage.getItem(key[string])

//通过记录名称集合（数组）获取sessionStorage信息，结果为数组
this.$sessionStorage.getItemsByKeys(keys[array])

//通过匹配记录名称获取sessionStorage信息，结果为数组
this.$sessionStorage.getArr(prex[string])

//通过记录名称删除sessionStorage信息
this.$sessionStorage.removeItem(key[string])

//删除所有记录
this.$sessionStorage.clear()
```



### LsyStorage部分

```
//设置localStorage信息，key为记录名称（字符串），value为字（可以是字符串或者对象）
this.$localStorage.setItem(key[string], value[string|object])

//设置localStorage信息，prex为记录前缀名（字符串），values为需要存储的信息集合（数组），byId表示是否以被存储对象的ID为后缀名或者说为下标（boolean)
this.$localStorage.setArr(prex[string], values[array],byId[boolean])

//通过数组与数组映射的方式存储信息，要求两数组长度相等，且keys内部元素为字符串类型
this.$localStorage.setList(keys[array], values[array])

//通过记录名称获取localStorage信息
this.$localStorage.getItem(key[string])

//通过记录名称集合（数组）获取localStorage信息，结果为数组
this.$localStorage.getItemsByKeys(keys[array])

//通过匹配记录名称获取localStorage信息，结果为数组
this.$localStorage.getArr(prex[string])

//通过记录名称删除localStorage信息
this.$localStorage.removeItem(key[string])

//删除所有记录
this.$localStorage.clear()
```
