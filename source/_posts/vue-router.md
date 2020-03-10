---
title: Vue路由使用以及参数传递
date: 2020-3-10
tags: [es6]
---
### Vue路由使用以及参数传递

- 安装
 
  - npm install vue-router

- 简单操作使用
    ```
    import Vue from 'vue'
    import VueRouter from 'vue-router'

    Vue.use(VueRouter)
    ```
- vue-router操作使用分解
    ```
    <div id="app">
        <h1>Hello App!</h1>
        <p>
            <!-- 使用 router-link 组件来导航，通过传入 `to` 属性指定链接，<router-link> 默认会被渲染成一个 `<a>` 标签 -->
            <router-link to="/foo">Go to Foo</router-link>
            <router-link to="/bar">Go to Bar</router-link>
        </p>
        <!-- 路由出口，路由匹配到的组件将渲染在这里 -->
        <router-view></router-view>
    </div>
    ```
- 定义路由 每个路由即为一个组件

    ```
    const routes = [
        { path: '/foo', component: Foo },
        { path: '/bar', component: Bar }
    ]
    ```
- 创建router实例

    ```
    const router = new VueRouter({
        routes // （缩写）相当于 routes: routes
    })
    ```
- 创建和挂载根实例
    ```
    const app = new Vue({
    　　el:'#app',
    　　router
    })  
    ```
- vue-router默认是hash模式,url:http://localhost:8000/#/hello
 如果想取消掉#,可以使用history模式，这样可以利用 history.pushState API完成url跳转无需重新加载页面
    ```
    const router = new VueRouter({
        mode: 'history',
        routes: [...]
    })
    ```
  那么url::http://localhost:8000/hello
  如果使用history模式,服务器端需要进行一些配置才可以,否则直接访问带参数的路由地址会返回404

 -  一些服务器端的配置
   -   apache 需要修改配置
       在项目目录下新建.htaccess文件(跟index.html同级)
        ```
        <IfModule mod_rewrite.c>
            RewriteEngine On
            RewriteBase /ibms/
            RewriteRule ^index\.html$ - [L]
            RewriteCond %{REQUEST_FILENAME} !-f
            RewriteCond %{REQUEST_FILENAME} !-d
            RewriteRule . /ibms/index.html [L]
        </IfModule>
        ```
        记得重启apache服务器
   -   nginx

        ```
        location / {
            try_files $uri $uri/ /index.html;
        }
        ```
   -   IIS服务器配置 <font color=red>注意:</font>IIS需要安装重写工具

        ```
        <?xml version="1.0" encoding="UTF-8"?>
        <configuration>
            <system.webServer>
                <rewrite>
                <rules>
                    <rule name="ReactRouter" patternSyntax="ECMAScript" stopProcessing="true">
                    <match url=".*" />
                    <conditions>
                        <add input="{HTTP_METHOD}" pattern="^GET$" />
                        <add input="{HTTP_ACCEPT}" pattern="^text/html" />
                        <add input="{REQUEST_FILENAME}" matchType="IsFile" negate="true" />
                    </conditions>
                    <action type="Rewrite" url="/index.html" />
                    </rule>
                </rules>
                </rewrite>
        </system.webServer>
        </configuration>
        ```

    为了防止404报错信息,可以在路由中配置
        ```
        const router = new VueRouter({
            mode: 'history',
            routes: [
                { path: '*', component: NotFoundComponent }
            ]
        })
        ```

- 重定向和别名

    - 重定向通过 routes 配置来完成，下面例子是从 /a 重定向到 /b

    ```
        const router = new VueRouter({
            routes: [
                { path: '/a', redirect: '/b' }
            ]
        })
    ```
    重定向的目标也可以是一个命名的路由：
    ```
    const router = new VueRouter({
        routes: [
            { path: '/a', redirect: { name: 'foo' }}
        ]
    })
    ```