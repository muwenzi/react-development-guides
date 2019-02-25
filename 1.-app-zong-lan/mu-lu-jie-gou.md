# 目录结构

## 原始的 Redux 项目目录结构

```text
Project/App
├── index.js                                      # 入口文件，包括App挂载，创建store
├── router.js                                     # App路由
├── manifest.json                                 # App的相关配置
├── components                                    # 业务型组件
│   └── Header                                    # 以<Header>组件为例
│       ├── Header.presentational.js              # 展示型组件
│       ├── Header.contianer.js                   # 容器型组件
│       ├── Header.less                           # 样式文件
│       └── __tests__                             # 测试
│           ├── __snapshots__                     # 快照测试文件夹，自动生成
│           ├── Header.presentational.test.js     # 展示型组件测试
│           └── Header.contianer.test.js          # 容器型组件测试 
├── widgets                                       # 小控件，自定义的基础ui组件
│   └── Button                                    # 以<Button>组件为例
│       ├── Button.widget.js                       
│       ├── Button.widget.less                     
│       └── __tests__                              
│           ├── __snapshots__                      
│           └── Button.widget.test.js                
├── states                                        # 状态管理相关，主要是Redux
│   ├── actions                                  
│   │   ├── sync                                  # 同步action
│   │   │   ├── actionOne.action.js              
│   │   │   ├── actionTwo.action.js              
│   │   │   ├── index.js                          # 将所有同步action聚合
│   │   │   └── __tests__                          
│   │   │       ├── actionOne.action.test.js     
│   │   │       └── actionTwo.action.test.js      
│   │   └── async                                 # 异步action
│   │       ├── actionOne.action.js               
│   │       ├── actionTwo.action.js               
│   │       ├── index.js                          # 将所有异步action聚合
│   │       └── __tests__                          
│   │           ├── actionOne.action.test.js      
│   │           └── actionTwo.action.test.js      
│   ├── middlewares                               # 中间件
│   │   ├── middlewareOne.middleware.js              
│   │   ├── middlewareTwo.middleware.js              
│   │   ├── index.js                              # 将所有中间件聚合
│   │   └── __tests__                              
│   │       ├── middlewareOne.middleware.test.js     
│   │       └── middlewareTwo.middleware.test.js      
│   ├── reducers                                    
│   │   ├── reducerOne.reducer.js              
│   │   ├── reducerTwo.reducer.js              
│   │   ├── index.js                              # 将所有异步reducer聚合
│   │   └── __tests__                              
│   │       ├── reducerOne.reducer.test.js     
│   │       └── reducerTwo.reducer.test.js      
│   ├── selectors                                                           
│   │   ├── selectorOne.selector.js              
│   │   ├── selectorTwo.selector.js              
│   │   ├── index.js                              # 将所有异步selector聚合
│   │   └── __tests__                              
│   │       ├── selectorOne.selector.test.js     
│   │       └── selectorTwo.selector.test.js     
│   ├── types                             
│   │   ├── typeOne.type.js              
│   │   ├── typeTwo.type.js              
│   │   ├── index.js                              # 将所有异步type聚合
│   │   └── __tests__                              
│   │       ├── typeOne.type.test.js     
│   │       └── typeTwo.type.test.js  
├── apis                                           
│   ├── apiOne.api.js              
│   ├── apiTwo.api.js              
│   ├── index.js                                  # 将所有api聚合
│   └── __tests__                              
│       ├── apiOne.api.test.js     
│       └── apiTwo.api.test.js     
└── utils                                         # 一些公共的工具类文件
    ├── utilOne.util.js              
    ├── utilTwo.util.js              
    ├── index.js                                  # 将所有util聚合
    └── __tests__                              
        ├── utilOne.util.test.js     
        └── utilTwo.util.test.js                          
```

## [Rematch](https://github.com/rematch/rematch) 封装的 Redux 项目结构

// TODO

