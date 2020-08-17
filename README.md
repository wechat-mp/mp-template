## 开发指南（WIP）
> 无特殊说明，以下命令行操作均在项目根目录(/path/to/project-name/)下进行。
### 环境依赖
>$ npm install
### 构建
#### 开发
>$ npm run watch
#### 发布
>$ npm run build
#### mock
> TODO
## 工程目录规范
```
├── doc              文档
├── miniprogram      构建产物
├── mock             假数据服务
├── config           工程编译配置
├── src              源码目录
  ├——components
    ├——biz
    ├——ui
  ├── common          应用级公共模块目录
    ├── utils       工具函数组件
    ├── config      配置模块
    ├── constants   常量模块
    ├── 其他...
  ├── pages         主包页面目录
    ├——components
    ├── common      分包级公共模块，结构参见应用级common
    ├── goods       子页面 pages/goods/index
      ├── common    页面级公共模块，结构参见应用级common
        ├——components
        ├——...
      ├── index.less
      ├── index.ts
      ├── index.wxml
      ├── index.json
      ├── README.md
  ├── packageOther    子包页面目录，结构参见pages
  ├── app.ts
  ├── app.json
  ├── app.less
```

## 开发规范
### 命名规范
- 分包：全小写，中划线连接；
> 例如 package-other
- 页面/组件文件夹：全小写，中划线连接；
> 例如 order-sure
- 文件：全小写，中划线连接；
> 例如 order-helper.ts
- 方法名/变量名：驼峰；
> const userName = '艾纹';
- className: 全小写，中划线连接。
> .p-h__body--active {
> color: red;
> }
### 组件开发规范
> - 页面组件放入页面内components里，理论上不能出现纯UI组件，因此components里无ui、biz目录；
> - 公共组件放入src/components，纯UI放入ui目录、包含业务逻辑放入biz目录。

### 页面开发规范
#### README.md
##### 必须包含页面传入入参
例如：pages/goods/index
- spuId（商品id）
##### 必须备注当前页面可能的上游页面
例如：pages/goods/index
- launch(表示当前页面可能会被启动时就打开)
- pages/home/index
##### 必须备注当前页面可能的下游页面
例如：pages/goods/index
- pages/order-sure/index?spuId=1(spuId:商品Id)
### 分包开发规范
> TODO