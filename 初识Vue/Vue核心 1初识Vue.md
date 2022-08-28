# Vue核心 Vue简介 初识Vue

## 1.1简介

### 	1.1.1.官网

- [英文官网]: https://vuejs.org/

- [中文官网]: https://cn.vuejs.org/

### 	1.1.2.介绍与描述

- <u>Vue</u> 是一套**动态构建用户界面**的**渐进式** JavaScript框架

  1. **构建用户界面：**把数据通过某种办法变成用户界面
  2. **渐进式**：Vue可以自底向上逐层的应用，简单应用只需要一个轻量小巧的核心库，复杂应用可以引入各式各样的Vue插件

- 作者：尤雨溪

  ![image.png](https://cdn.nlark.com/yuque/0/2022/png/1379492/1643034892163-5a414e93-a9a1-45c1-ad72-89bbf4f4eba5.png?x-oss-process=image%2Fresize%2Cw_937%2Climit_0)

### 	1.1.3.Vue的特点

1.遵循MVVM模式 

2.编码简洁，体积小，运行效率高，适合移动/PC端开发 

3.它本身只关注 UI，可以引入其它第三方库开发项目

4.采用组件化模式，提高代码复用率、且让代码更好维护

![image.png](https://cdn.nlark.com/yuque/0/2022/png/1379492/1643035195917-eb463d5c-5a77-43a6-914e-dd0f83b0ff80.png?x-oss-process=image%2Fresize%2Cw_582%2Climit_0)



5.声明式编码，让编码人员无需直接操作DOM，提高开发效率

![image.png](https://cdn.nlark.com/yuque/0/2022/png/1379492/1643035526209-9cdf929a-b3db-4997-b1fe-74fd203037d8.png?x-oss-process=image%2Fresize%2Cw_750%2Climit_0)



●使用虚拟DOM 和 Diff算法，尽量复用DOM节点

![image.png](https://cdn.nlark.com/yuque/0/2022/png/1379492/1643035897962-d84f5075-0fd7-4d52-ad8c-31371d98bb08.png?x-oss-process=image%2Fresize%2Cw_750%2Climit_0)



### 1.1.4.与其他JS框架的关联 

●借鉴 angular 的 模板 和 数据绑定 技术

●借鉴 react 的 组件化 和 虚拟DOM 技术

### 1.1.5.Vue 周边库

●vue-cli：vue 脚手架

●vue-resource(axios)：ajax 请求

●vue-router：路由

●vuex：状态管理（它是 vue 的插件但是没有用 vue-xxx 的命名规则）

●vue-lazyload：图片懒加载

●vue-scroller：页面滑动相关

●mint-ui：基于 vue 的 UI 组件库（移动端）

●element-ui：基于 vue 的 UI 组件库（PC 端）

## 1.2初识 Vue

**前置工作**

1.给浏览器安装 [Vue Devtools](https://cn.vuejs.org/v2/guide/installation.html#Vue-Devtools) 插件
		2.标签引入Vue包
		3.（可选）阻止vue在启动时生成生产提示Vue.config.productionTip = false
		4.favicon 需要将页签图标放在项目根路径，重新打开就有了（shfit+F5 强制刷新）
		**初识Vue**
		1.想让Vue工作，就必须创建一个Vue实例，且要传入一个**配置**对象
		2.root 容器里的代码依然符合html规范，只不过混入了一些特殊的Vue语法
		3.root 容器里的代码被称为Vue模板
		4.Vue 实例与容器是一一对应的
		5.真实开发中只有一个Vue实例，并且会配合着组件一起使用
		6.{{xxx}}中的 xxx 要写 **js 表达式**，且 xxx 可以自动读取到data中的所有属性
**注意区分**：js 表达式 和 js代码（语句）
a.表达式：一个表达式会产生一个值，可以放在任何一个需要值的地方
	a	a+b		demo(1)		x === y ? 'a' : 'b'
b.<u>js代码（语句）</u>
	if(){}		for(){}
7一旦data中的数据发生变化，那么模板中用到该数据的地方也会自动更新

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<script src="../js/vue.js" type="text/javascript" charset="utf-8"></script>
	</head>
	<body>
		<!-- 准备一个容器 -->
		<div id="root">
			<h1>173,{{name.toUpperCase()}},{{age}}</h1>
		</div>
	<script type="text/javascript">
		Vue.config.productionTip=false //阻止vue在启动时生成生产提示。

		
		//创建Vue实例
		new Vue({
			el:'#root',		//el用于指定当前Vue实例为那个容器服务，值通常为css选择器字符串	document.getElementsByName
			data:{	//data中用于存储数据，数据供el指定的容器去使用，值我们暂时先写成一个对象
				name:'qishan',
				age:'18'
			}
		})
	
	</script>
	</body>
</html>

```

**运行结果：**<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220828175657308.png" alt="image-20220828175657308" style="zoom: 50%;" />
