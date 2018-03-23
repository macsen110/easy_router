# yao-easy-router 简单易用的路由系统

## Installation && Use

```bash
npm i yao-easy-router --save

import router form 'yao-easy-router' 

var config = [
    {
        name: 'home',
        component: (obj, component, title) => {},
        title: '首页'
    },
    {
        name: 'list',
        component: {
            init: () => {},
            destory: () => {}
        },
        title: '列表页'
    }
]
router.config(config)

```

或者使用require加载

```bash
npm i yao-easy-router --save

var router = require('yao-easy-router')

```

或者直接script 标签引入 npm包目录下的index.js

```js

<script src="./index.js"></script>

```

全局配置路由信息,路径,
```
const routerConfig = [
    {
        name: 'home',
        component: (obj, component, title) => {},
        title: '首页'
    },
    {
        name: 'list',
        component: {
            init: () => {},
            destory: () => {}
        },
        title: '列表页'
    }
]
YAO_EASY_ROUTER._init(routerConfig)

```

可以异步使用promise加载组件,component 设置为对象添加_Promise属性,比如配合
bundle-loader模块异步加载组件

```
var loadAsync = function(obj) {
    return {
      _Promise: function() {
        return new Promise(function(res, rej) {
          var load = require("bundle-loader?lazy&name=[name]!./pages/" +
            obj.pageName +
            ".js");
          load(function(commponent) {
            res(commponent);
          });
        });
      }
    };
  };
  routerConfig.forEach(function(item, idx) {
    item.component = loadAsync(item);
  });
```

属性
* _config 内置的配置对象

    *_root 页面中路由容器的根节点,
    路由跳转会清空此节点中的旧路由dom，加载新路由对应的dom

例如
```

YAO_EASY_ROUTER._config._root = document.getElementById('app');

```
方法:

go(name:String, params:Object)
跳转下一个页面,
```
router.go('index')//跳转到首页
router.go('detail', {id: 3})//跳转到详情页,id为3
```

router.replace(name:String, params:Object)
替换一个新页面,用法同上

## Document


Demo地址 
Contact 

* email 839945193@qq.com or liangyusen1202@gmail.com
