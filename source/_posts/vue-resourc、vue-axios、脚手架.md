# vue 的获取数据
## vue-resource

	mount(){
		this.getdata()
	},
	methods:{
		getdata(){
		//方法一：
			this.$http.post('http://route.showapi.com/1211-1?showapi_appid=46452&count=5&showapi_sign=c3bc2247155b4219bffb60cac4fd315c')
			.then(res=>{console.log(res)})
		}
		//方法二：
			this.$http.get('http://route.showapi.com/1211-1',
			{
				params:{
					showapi_appid:245372,
					showapi_sign:'b2f6f519a25f4c7e81e3ea6c4ee7ac14'
				}
			}).then(res=>{console.log(res)})
		}
	}
## axios

	mount(){
		this.getdata()
	},
	methods:{
		getdata(){
		方法一：
			axios.post('http://route.showapi.com/1211-1?showapi_appid=46452&count=5&showapi_sign=c3bc2247155b4219bffb60cac4fd315c')
			.then(res=>{console.log(res)})
		}
		方法二：
			axios.get('http://route.showapi.com/1211-1',
			{
				params:{
					showapi_appid:245372,
					showapi_sign:'b2f6f519a25f4c7e81e3ea6c4ee7ac14'
				}
			}).then(res=>{console.log(res)})
		}
	}
## jsonp

	<input type="text" @keyup="getList()" v-model="inptext">
	<ul>
		<li v-for="(item,index) in list" :key="index">{{item}}</li>
	</ul>
	data: {
		inptext:'',
		list:[]
	},
	mounted() {},
	methods:{
		getList(){ 					this.$http.jsonp('https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su',{
				params:{
					wd:this.inptext
				},jsonp:'cb'
			}).then(res => {
					console.log(res);
					this.list = res.body.s
				})
			}
		}
## vue脚手架搭建

	1、检测node
		node -v
	2、检测npm
		npm -v
	3、安装淘宝镜像（有就可以不用执行）
		npm install -g cnpm --registry=https://registry.npm.taobao.org
	4、全局安装vuecli
		cnpm install vue-cli -g
	5、初始化项目
		vue init webpack 脚手架文件名(例如：vuetest)
		注意：在vue-router？一项选择“y”其他的都是选择“n”
	6、进入项目
		cd vuetest
	7、安装模板（每次从git中拉取vue脚手架时都要安装模板，第一次安装vue时可省略）
		cnpm install
	8、运行项目
		cnpm run dev 或 npm run dev