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
window.YAO_EASY_ROUTER.config(config)

```


## Document


Demo地址 
Contact 

* email 839945193@qq.com or liangyusen1202@gmail.com
