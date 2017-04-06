# deploy-ftp-webpack-plugin
使用ftp上传文件的webpack插件
## Usage
在webpack的配置文件使用此插件
```
var DeployFtpWebpackPlugin = require('./deploy.plugin');
module.exports = {
    plugins: [
        new DeployFtpWebpackPlugin({
            host:'',
            port:'',
            user:'',
            password:'',
            secure:true
        }, {
            fromPath:'./dist',
            destPath:'/f2e/products/vuetodo/',
            exclude:/\.html$/

        })
    ]
};

```
## Configuration 
插件需要传递的参数DeployFtpWebpackPlugin(config, options)
config参数里是ftp需要的参数，options是配置文件的参数
1. config
- host: 服务器地址
- port: 服务端口号
- user: 服务器登录用户名
- password: 服务器登录密码
- secure: 是否加密
2. options
 - fromPath: 需要上传的文件路径
 - destPath: 上传到服务器的目标文件路径
 - exclude: 正则表达式，需要排除的文件，比如不想上传以html格式的文件(/\.html$/)
