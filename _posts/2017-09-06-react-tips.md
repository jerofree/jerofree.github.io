---
layout: post
title:  "React使用注意事项"
category: 
tags: []
---
## 	render函数中的返回值，return 只能有一个根标签，因为函数只能return一次,编译后会return两次, 
	return后的括号或者标签的开始要和return在同一行，否则编译会报错。
	
##	在 JSX 中使用表达式
	你可以任意地在 JSX 当中使用 JavaScript 表达式，在 JSX 当中的表达式要包含在大括号里。
	
##  JSX 属性
	你可以使用引号来定义以字符串为值的属性：
	const element = <div tabIndex="0"></div>;
	也可以使用大括号来定义以 JavaScript 表达式为值的属性：
	const element = <img src={user.avatarUrl}></img>;
	
## JSX 嵌套
	如果 JSX 标签是闭合式的，那么你需要在结尾处用 />, 就好像 XML/HTML 一样：
	const element = <img src={user.avatarUrl} />;	
	警告:
	因为 JSX 的特性更接近 JavaScript 而不是 HTML , 所以 React DOM 使用 camelCase 小驼峰命名 
	来定义属性的名称，而不是使用 HTML 的属性名称。
例如，class 变成了 className，而 tabindex 则对应着 tabIndex.

## 	组件 & Props
	组件可以将UI切分成一些的独立的、可复用的部件，这样你就只需专注于构建每一个单独的部件。
	组件从概念上看就像是函数，它可以接收任意的输入值（称之为“props”），并返回一个需要在页面上展示的React元素。
	
##  函数定义/类定义组件
	定义一个组件最简单的方式是使用JavaScript函数：
	function Welcome(props) {
   return <h1>Hello, {props.name}</h1>;
   }
	该函数是一个有效的React组件，它接收一个单一的“props”对象并返回了一个React元素。我们之所以称这种类型的组件为函数
	定义组件，是因为从字面上来看，它就是一个JavaScript函数  
	
##  组件渲染
		在前面，我们遇到的React元素都只是DOM标签：
		const element = <div />;
		然而，React元素也可以是用户自定义的组件：
		const element = <Welcome name="Sara" />;
		当React遇到的元素是用户自定义的组件，它会将JSX属性作为单个对象传递给该组件,这个对象称之为“props”。
		警告:
	   组件名称必须以大写字母开头。
	   例如，<div />表示一个DOM标签，但<Welcome />表示一个组件并限定了它的可用范围。
	   



	



		


	






