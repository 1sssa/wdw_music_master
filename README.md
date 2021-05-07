### wdw-music-一个基于vue的高仿网易云音乐网站

#### (http://8.129.133.120/)
(线上演示地址)


## 快速启动

`当前项目目录下,路径输入cmd进入命令行`

当前目录终端```
npm install     # 安装项目所需的依赖(如果速度过慢, 可以尝试cnpm或者使用代理)
npm run serve   #启动项目服务
```

浏览器打开输入http://localhost:8080网站就能打开哟(注意查看main.js的路径查看接口地址，localhost:3000是后端下载到本地开启，使用云端的api的话需要去配置哦，配置目录node_modules>@vue>cli-service>lib>option.js,找到devServer,修改为
      devServer: {
        disableHostCheck: true,
        proxy: { //解决跨域问题
            '/api': {
                // 此处的写法，目的是为了 将 /api 替换成 https://autumnfish.cn/
                target: 'https://autumnfish.cn/',
                // 允许跨域
                changeOrigin: true,
                ws: true,
                pathRewrite: {
                    '^/api': ''
                }
            }
        },
        port: 8081
    })
不要直接使用云端地址哦，不然会有跨域问题。

 **API安装步骤：** 

1. git clone https://github.com/Binaryify/NeteaseCloudMusicApi.git

(不会使用git的小伙伴可以直接去上面的接口仓库下载接口哦)

2. npm install

3.cd api文件夹

4.node app.js
