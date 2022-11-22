1、设置环境

安装node ，并设置npm 国内镜像环境  npm config set registry https://registry.npm.taobao.org

2、创建基于typescript的node项目

```bash
npm init   -yes   //初始化当前目录，生成package.json
npm install --save-dev @types/node   //安装开发node依赖
npm install typescript --save-dev    //安装typescript依赖
npm install --save-dev ts-node nodemon  //安装ts-node编译和 node自动热加载控件

npx tsc --init --rootDir src --outDir build --esModuleInterop --resolveJsonModule --lib es6 --module commonjs --allowJs true --noImplicitAny true   //创建tsconfig.json文件
```

3、配置启动脚本

在package.json中添加 script启动脚本

```json
{
  "name": "node_test",
  "version": "1.0.0",
  "description": "",
  "scripts": {
    "dev": "nodemon --watch src -e ts,tsx --exec ts-node src/index.ts",
    "build": "tsc",
    "start": "node build/index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@types/node": "^18.11.9",
    "ts-node": "^10.9.1",
    "nodemon": "^2.0.20",
    "typescript": "^4.8.4"
  }
}
```
4、运行node

npm run  dev   //运行src/index.ts入口文件，文件变化后重新运行

npm run build   //编译文件

npm run start   //运行编译后的文件






