# table-tree 

##  前言

公司想搞个表格树的展示页面，看着element有个表格树，还以为可以用。

用出来只用表格没有树，研究半天没研究个所以然，只能从新找个

npm里找到一个：vue-table-with-tree-grid

## 正文

### element的坑

​	element：http://element-cn.eleme.io/#/zh-CN/component/table

​	![1554963481714](https://img2018.cnblogs.com/blog/1416523/201904/1416523-20190411151707309-2031303153.png)

然后一模一样的代码用在项目中，标点符合都没改：

​	![1554964666704](https://img2018.cnblogs.com/blog/1416523/201904/1416523-20190411151805189-817678650.png)

emmmmmmmm。。。。最前面的箭头不见了。。。换了好几个系统试了一下。居然都没有。。

毫不犹豫投入了vue-table-with-tree-grid的怀抱

### vue-table-with-tree-grid

​	npm中它的地址：https://www.npmjs.com/package/vue-table-with-tree-grid

#### 安装


```
npm i vue-table-with-tree-grid -S
```

Or use yarn:

```
yarn add vue-table-with-tree-grid
```


#### 导入


```
import Vue from 'vue'
import ZkTable from 'vue-table-with-tree-grid'
 
Vue.use(ZkTable)
```

Or

```
import Vue from 'vue'
import ZkTable from 'vue-table-with-tree-grid'
 
Vue.component(ZkTable.name, ZkTable)
```


#### 示例：

https://github.com/MisterTaki/vue-table-with-tree-grid/blob/master/example/Example.vue

DOM

```<zk-table

​        ref="table"

​        :data="data"

​        :columns="columns"

​        :stripe="props.stripe"

​        :border="props.border"

​        :show-header="props.showHeader"

​        :show-summary="props.showSummary"

​        :show-row-hover="props.showRowHover"

​        :show-index="props.showIndex"

​        :tree-type="props.treeType"

​        :is-fold="props.isFold"

​        :expand-type="props.expandType"

​        :selection-type="props.selectionType"

​        sum-text="sum"

​        index-text="#"/>```

数据

​	```props: {

​        stripe: false,

​        border: false,

​        showHeader: true,

​        showSummary: false,

​        showRowHover: true,

​        showIndex: false,

​        treeType: true,

​        isFold: true,

​        expandType: false,

​        selectionType: false

​      },

​      data: [

​        {

​          name: 'Jack',

​          sex: 'male',

​          likes: ['football', 'basketball'],

​          score: 10,

​          children: [

​            {

​              name: 'Ashley',

​              sex: 'female',

​              likes: ['football', 'basketball'],

​              score: 20,

​              children: [

​                {

​                  name: 'Ashley',

​                  sex: 'female',

​                  likes: ['football', 'basketball'],

​                  score: 20

​                },

​                {

​                  name: 'Taki',

​                  sex: 'male',

​                  likes: ['football', 'basketball'],

​                  score: 10,

​                  children: [

​                    {

​                      name: 'Ashley',

​                      sex: 'female',

​                      likes: ['football', 'basketball'],

​                      score: 20

​                    },

​                    {

​                      name: 'Taki',

​                      sex: 'male',

​                      likes: ['football', 'basketball'],

​                      score: 10,

​                      children: [

​                        {

​                          name: 'Ashley',

​                          sex: 'female',

​                          likes: ['football', 'basketball'],

​                          score: 20

​                        },

​                        {

​                          name: 'Taki',

​                          sex: 'male',

​                          likes: ['football', 'basketball'],

​                          score: 10

​                        }

​                      ]

​                    }

​                  ]

​                }

​              ]

​            },

​            {

​              name: 'Taki',

​              sex: 'male',

​              likes: ['football', 'basketball'],

​              score: 10

​            }

​          ]

​        },

​        {

​          name: 'Tom',

​          sex: 'male',

​          likes: ['football', 'basketball'],

​          score: 20,

​          children: [

​            {

​              name: 'Ashley',

​              sex: 'female',

​              likes: ['football', 'basketball'],

​              score: 20,

​              children: [

​                {

​                  name: 'Ashley',

​                  sex: 'female',

​                  likes: ['football', 'basketball'],

​                  score: 20

​                },

​                {

​                  name: 'Taki',

​                  sex: 'male',

​                  likes: ['football', 'basketball'],

​                  score: 10

​                }

​              ]

​            },

​            {

​              name: 'Taki',

​              sex: 'male',

​              likes: ['football', 'basketball'],

​              score: 10,

​              children: [

​                {

​                  name: 'Ashley',

​                  sex: 'female',

​                  likes: ['football', 'basketball'],

​                  score: 20

​                },

​                {

​                  name: 'Taki',

​                  sex: 'male',

​                  likes: ['football', 'basketball'],

​                  score: 10

​                }

​              ]

​            }

​          ]

​        },

​        {

​          name: 'Tom',

​          sex: 'male',

​          likes: ['football', 'basketball'],

​          score: 20

​        },

​        {

​          name: 'Tom',

​          sex: 'male',

​          likes: ['football', 'basketball'],

​          score: 20,

​          children: [

​            {

​              name: 'Ashley',

​              sex: 'female',

​              likes: ['football', 'basketball'],

​              score: 20

​            },

​            {

​              name: 'Taki',

​              sex: 'male',

​              likes: ['football', 'basketball'],

​              score: 10

​            }

​          ]

​        }

​      ],

​      columns: [

​        {

​          label: 'name',

​          prop: 'name',

​          width: '400px'

​        },

​        {

​          label: 'sex',

​          prop: 'sex',

​          minWidth: '50px'

​        },

​        {

​          label: 'score',

​          prop: 'score'

​        },

​        {

​          label: 'likes',

​          prop: 'likes',

​          minWidth: '200px',

​          type: 'template',

​          template: 'likes'

​        }

​      ],

​      text1: this.$store.getters.code,

​      tableData: [],

​      currentPage: 1,

​      total: 0,

​      pageSize: 10,

​      loading: false,

​      defaultProps: {

​        children: 'children',

​        label: 'label'

​      }```



#### 显示效果：

![1554964329215](https://img2018.cnblogs.com/blog/1416523/201904/1416523-20190411152228749-230282404.png)



完结。撒花。。



## 递归处理树形数据

用树形数据的时候经常会需要为树形数据修改值，增加值之类的

示例

```

respose.data // 我是树形数据

//遍历

for (let i = 0, len = respose.data.length; i < len; i++) {

​              readTree(respose.data[i])

​            }



const readTree = function(node) {

​        node.flag === '0' ? node.flag1 = '我是flag1的值1' : node.flag1 = '我是flag1的值2'

​        node.label = `我是label 的新值`

​        if (node.children && node.children.length > 0) {

​          for (let i = 0, len = node.children.length; i < len; i++) {

​            readTree(node.children[i])

​          }

​        }

​      }

```

## 原始数据转树形数据

```

//data为原始数据，root最大的根节点，idTxt为本身标识, pidTxt为父级标识, pushTxt为子级标识

getTree(data, root, idTxt, pidTxt, pushTxt) {

​      // 递归方法

​      function getNode(id) {

​        var node = []

​        for (var i = 0; i < data.length; i++) {

​          if (data[i][pidTxt] === id) {

​            data[i][pushTxt] = getNode(data[i][idTxt])

​            node.push(data[i])

​          }

​        }

​        if (node.length === 0) {

​          return

​        } else {

​          return node

​        }

​      }

​      // 使用根节点

​      return getNode(root)

​    }

```

```

//原始数据：

```
{"id":1,"pId":0,"name":"父节点1 - 展开","open":true},
  {"id":11,"pId":1,"name":"父节点11 - 折叠"},
  {"id":12,"pId":1,"name":"父节点12 - 折叠"},
  {"id":13,"pId":1,"name":"父节点13 - 没有子节点"},
  {"id":2,"pId":0,"name":"父节点2 - 折叠"},
  {"id":21,"pId":2,"name":"父节点21 - 展开","open":true},
  {"id":22,"pId":2,"name":"父节点22 - 折叠"},
  {"id":23,"pId":2,"name":"父节点23 - 折叠"},
  {"id":3,"pId":0,"name":"父节点3 - 没有子节点"}
```

```
//处理后的数据
[
  {
    "id": 1,
    "pId": 0,
    "name": "父节点1 - 展开",
    "open": true,
    "children": [
      {
        "id": 11,
        "pId": 1,
        "name": "父节点11 - 折叠"
      },
      {
        "id": 12,
        "pId": 1,
        "name": "父节点12 - 折叠"
      },
      {
        "id": 13,
        "pId": 1,
        "name": "父节点13 - 没有子节点"
      }
    ]
  },
  {
    "id": 2,
    "pId": 0,
    "name": "父节点2 - 折叠",
    "children": [
      {
        "id": 21,
        "pId": 2,
        "name": "父节点21 - 展开",
        "open": true
      },
      {
        "id": 22,
        "pId": 2,
        "name": "父节点22 - 折叠"
      },
      {
        "id": 23,
        "pId": 2,
        "name": "父节点23 - 折叠"
      }
    ]
  },
  {
    "id": 3,
    "pId": 0,
    "name": "父节点3 - 没有子节点"
  }
]
```


## 完结 ，撒花
