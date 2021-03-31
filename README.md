# lerna 常用命令

- 创建一个新的由 `lerna`  管理的包

```js
lerna create
```

- 安装所有依赖项并连接所有的交叉依赖

```js
lerna bootstrap
```

- 增加模块包到最外层的公共 `node_modules`  中

```js
lerna add <package-name> // eg: lerna add axios
```

- 增加模块包到 `packages`  中指定项目

```js
// eg: 将 ui-web 模块增加到 example-web 项目中
lerna add ui-web --scope=example-web
```

- 在 `packages`  中对应包下的执行任意命令

```js
// eg: 执行 packages 下 example-web 项目中的 yarn start 命令
// 常用的可以将它配置到最外层的 package.json 中
lerna exec --scope example-web -- yarn start

// 如果命令中不增加 --scope example-web
// 直接使用下面的命令，这会在 packages 下所有包执行命令rm -rf ./node_modules
lerna exec -- rm -rf ./node_modules
```

- 显示所有的安装的包

```js
// 等同于 lerna list
lerna ls
```

- 从所有包中删除 node_modules 目录

```js
// 注意下 lerna clean 不会删除项目最外层的根 node_modules
lerna clean
```

- 在当前项目中发布包

```js
lerna publish
```
