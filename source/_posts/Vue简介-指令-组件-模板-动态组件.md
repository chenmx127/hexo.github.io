# Vue.js
## 1、简介
	Vue是一套用于构建用户界面的渐进式框架。Vue核心库只关注视图层。
## 2、指令(大都放在挂载点中)
### v-text   --直接显示内容不会去解析HTML标签

	挂载点中代码：
	<div v-text="text"></div>
	Vue中代码：
	data:{
		text:"<p>这是一个测试</p>"
	}
### v-html   --解析HTML标签

	挂载点中代码：
	<div v-html="text"></div>
	Vue中代码：
	data:{
		text:"<p>这是一个测试</p>"
	}
### v-on (也可以用“@”表示)
绑定事件监听器。事件类型由参数指定。表达式可以是一个方法的名字或一个内联语句，如果没有修饰符也可以省略。
	
	挂载点中代码：
	<input type="button" value="点击+" v-on:click="add()">
	<input type="button" value="点击-" @click="del()">{{num}}
	Vue中代码：
	data:{
		num:1
	},
	methods:{
		add(){this.num++;},
		del(){this.num--;}
	}

### v-show   ---值为：true /false
可以对标签进行隐藏（false）显示（true）
	
	挂载点中代码：
	<div class="box" v-show="isSeen"></div>
	Vue中代码：
	data:{
		isSeen:true
	}
### v-on与v-show配合用

	挂载点中代码：
	<input type="button" value="点一下" @click="isShow()">
	<div class="box" v-show="isSeen"></div>
	Vue中代码：
	data:{
		isSeen:true
	},
	methods:{
		isShow(){
			this.isSeen=!this.isSeen
		}
	}
### v-if v-else-if v-else    ---进行判断
与v-show不同的是它只执行对应情况的代码，其他选择不执行。
	
	挂载点中代码：
	<div v-if="num==0">这是0</div>
	<div v-else-if="num==1">这是1</div>
	<div v-else>这是其他情况</div>
	Vue中代码：
	data:{
		num:0
	}
### v-model    --显示出在标签中输入的内容
只在input标签、select标签、textarea标签以及components（组件）中使用。
	
	挂载点中代码：
	<input v-model="text">{{text}}
	Vue中代码：
	data:{
		text:""
	}
### v-for    --格式要严谨
基于源数据多次渲染元素或模板块。此指令之值，必须使用特定语法 alias in expression。
	
	挂载点中代码：
	<div v-for="(name,index) in obj" :key="index"></div>
	Vue中代码：
	data:{
		pome:['鹅鹅鹅','曲项向天歌','白毛浮绿水','红掌拨清波'],
		obj:[{name:"张三",img:"./img/cao.jpg"},
			{ name: "李四", img: "./img/cao.jpg" }, 
			{ name: "王五", img: "./img/cao.jpg" }]
		}
### v-bind (可以简写为：“:”)
动态地绑定一个或多个 attribute

	挂载点中代码：
	<img :src="name" width="200px">
	Vue中代码：
	data:{
		name:"./img/cao.jpg"
	}
### template    --模板
一个字符串模板作为 Vue 实例的标识使用。模板将会替换挂载的元素。挂载元素的内容都将被忽略，除非模板的内容有分发插槽。其中内容必须用一个div包裹。
	
	挂载点中代码：
	<div id="app">今天天气真好！</div>
	写法一：
	<script type="x-template" id="name">
		<div>这是内容：{{message}}</div>
	</script>
	写法二：
	<template id="name">
		<div>这是内容：{{message}}</div>
	</template>
	Vue中代码：
	data:{
		message:"这是主体"
	},
	template:"#name",

### v-slot    --和组件搭配使用
一般用于template模板中。v-slot中有name属性可以在组件中用slot="name值"进行调用，将组件中的内容替换模板中的内容。要想改变组件中内容的顺序，可以将模板中的slot标签顺序进行调换。

	挂载点中代码：
	<hello>
		<h1>这是标题</h1>
		<div>这是内容1</div>
		<div>这是内容2</div>
	</hello>
	<template id="box">
		<div><slot></slot></div>
	</template>
	Vue中代码：
	components:{
		"hello":{template:"#box"}
	}
### 动态组件
类似选项卡操作可以用Vue中的component 元素加一个特殊的 is attribute 来实现。

	挂载点中代码：
	<input type="button" value="点击1" @click="message='hello'">
	<input type="button" value="点击2" @click="message='world'">
	<component :is= "message"></component>
	Vue中代码：
	data:{
		message:"hello"  
	},
	components:{
		"hello":{template:`<div><p>这是我要的<p></div>`},
		"world":{template:`<div><p>你想说什么<p></div>`}
	}