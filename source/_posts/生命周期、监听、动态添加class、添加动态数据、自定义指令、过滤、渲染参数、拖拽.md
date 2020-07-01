# Vue
## 生命周期（钩子函数）
所有的生命周期钩子自动绑定 this 上下文到实例中，因此你可以访问数据，对 property 和方法进行运算。
### beforeCreate
它是在创建实例之前调用。
### created
在创建完成实例之后调用。
### beforeMount
在挂载开始之前被调用。
### mounted
在实例被挂载完成之后调用。mounted 不会保证所有的子组件也都一起被挂载。
### beforeUpdate
在数据更新时调用，发生在虚拟 DOM 打补丁之前。这里适合在更新之前访问现有的 DOM。
### updated
当这个钩子被调用时，组件 DOM 已经更新，所以你现在可以执行依赖于 DOM 的操作。
### beforeDestroy
实例销毁之前调用。在这一步，实例仍然完全可用。
### destroy
实例销毁后调用。该钩子被调用后，对应 Vue 实例的所有指令都被解绑，所有的事件监听器被移除，所有的子实例也都被销毁。
## render    --渲染函数
该渲染函数接收一个 createElement 方法作为第一个参数用来创建 VNode。可以在style标签中测试创建的class="box"属性是否可用。

	render(createElement){
		return createElement("ul",
			{
				class:"box",
				style:{
					background:"red",
					color:"yellow"
				},
				attrs:{
			 		ma:"nn"
				}
			},
			[
				createElement("li","这是一"),
				createElement("li", "这是二"),
				createElement("li","这是三"),
			])
		}
## vm.$watch    --进行监听
表达式只接受监督的键路径。为了发现对象内部值的变化，可以在选项参数中指定 deep: true。

	<h1>{{num}}</h1>
	<h1>{{xyz}}</h1>
	data:{
		num:123,
		xyz:546
	},
	vm.$watch("num",function(){
		alert("这是一个数");
		this.xyz=this.num+10;
	})
	document.onclick= function () {
		vm.num = 100
	}
## props    --给组件添加动态值
通过 v-bind 动态赋值。

props 可以是数组或对象，用于接收来自父组件的数据。props 可以是简单的数组，或者使用对象作为替代，对象允许配置高级选项，如类型检测、自定义验证和设置默认值。

type：可以是下列原生构造函数中的一种：String、Number、Boolean、Array、Object、Date、Function、Symbol、任何自定义构造函数、或上述内容组成的数组。

	<hello :title="title" :num="num" bood="{aa:'dassad'}"></hello>
	Vue.component('hello', {
		props: ['title', 'num','bood']
	})
	另一种写法：
	props: {
		title: String,
		likes: Number,
		isPublished: Boolean,
		commentIds: Array,
		author: Object,
		callback: Function,
		contactsPromise: Promise // or any other constructor
	}
## directives    --自定义指令
包含 Vue 实例可用指令的哈希表。类型为：Object。

	<div v-bb>这是一句话</div>
	Vue.directive("bb",{
		bind:function(el) {
			el.style.color = "yellow"
		}
	})
## filter    --过滤器
过滤器可以用在两个地方：双花括号插值和 v-bind 表达式。

	第一种：<div v-bind:id="text|aa"></div>
	第二种：{{text|aa}}
	data:{
		text:13
	},
	filters:{
		"aa":function(cc) {
			return cc<10?'0'+cc:'shu'+cc
		}
	}
## 动态添加class

	<div class="ss" :class="{obj:addclass}">这是扫十点四十</div>
	data: {
		addclass: true
	}
## 自定义指令--拖拽

	<div v-box></div>
	Vue.directive("box",{
		bind:function(el){
			el.style.width="200px",
			el.style.height="200px",
			el.style.background="#f00",
			el.style.position="absolute",
			el.style.top="0px",
			el.style.left="0px",
			el.onmousedown = function (event) {
				event = event || window.event;
				//获取当前鼠标距离滑块边框的top与left值
				var deltaX = event.clientX - el.offsetLeft;
				var deltaY = event.clientY - el.offsetTop;
				document.onmousemove = function (event) {
					event = event || window.event;
					//重新获取滑块距离浏览器的top与left值
					var x = event.clientX - deltaX;
					var y = event.clientY - deltaY;
					if (x < 0) x = 0;
					if (y < 0) y = 0;
					if (x > document.clientWidth - el.clientWidth) {
						x = document.clientWidth - el.clientWidth;
					}
					if (y > document.clientHeight - el.clientHeight) {
						y = document.clientHeight - el.clientHeight;
					}
					el.style.left = x + "px";
					el.style.top = y + "px";
				}
			},
			document.onmouseup = function () {
				document.onmousemove = null;
			}
		}
	})