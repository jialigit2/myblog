##Vue 插件

### scope 

官方插件的格式：
@vue/cli-plugin-*   依赖的格式是这样的

安装一个插件：

比如我们  

		vue add eslint  
		
这个命令将 @vue/eslint 解析为完整的包名 @vue/cli-plugin-eslint

这里面， @vue就是scope, 这表示是官方插件

如果不是官方插件，即第三方插件，不带@vue前缀

第三方插件，也可以定义自己的scope,也就是用自定义前缀  
比如：第三方插件 @foo/vue-cli-plugin-bar  ， 添加命令：

		vue add @foo/bar  
		


##preset
预定义属性和插件，为项目的默认配置集合


##CLI 服务
@vue/cli-service 插件vue-cli-service命令

		npm run serve  
		npx vue-cli-service serve

##浏览器兼容性 and Polyfill


##ES5, ES6, ES6+

module
export
import ... from ...
require
##babel 
transcompile

有了 Babel 我们可以兼顾所有最新的 ES2015+ 语言特性

现如今绝大多数现代浏览器都已经支持了原生的 ES2015，所以因为要支持更老的浏览器而为它们交付笨重的代码是一种浪费。


##css 预处理 post-css

![]()

> ******
> 
> 



**
> hjhh