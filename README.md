# 说明

微信小程序 通讯录列表、联系人(基于youzan)编辑、新增、导入到手机通讯录。事件总线的解耦方式，代码完全解耦，引入即可使用
 
# 使用文档
## 代码集成至已有项目
> 此项目整体上来说是个demo程序，核心的代码在pages/contacts中，集成方式需要将pages/contacts拷贝到目标项目中
## 使用方法
### 使用准备
#### app.json中注入contacts的页面
```

"pages":[
  "xxx/contacts/contacts",
  "xxx/contacts/example/pages/contact/index"
]
```
#### app.js注入事件总线
```
App({
   globalData: {
     bus: eventBus.eventBus
   }
})
```
#### app.wxss注入样式
```
@import "xxx/contacts/example/app.wxss";
```
`备注:xxx为contacts所在的目录相对路径`

### 事件总线文档

#### contacts 通讯录事件总线-发送端
> 事件名:点击联系人 contactsClicContact  
参数:联系人对象 contact

#### contacts 通讯录事件总线-接收端
> 事件名:更新联系人组 contactsUpdateGroups   
参数:联系人组 groups  
备注:groups 是一个contact数组，程序将会自动对contact进行pinyin分组




# 感谢
基于 [https://github.com/treadpit/wx_pinyin](https://github.com/treadpit/wx_pinyin)


