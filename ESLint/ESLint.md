# 安装
1. eslint
    1. 安装
        ```
        npm install -g eslint
        ```
    2. 新建.eslintrc文件
2. 标准配置
    1. 安装
        ```
        npm install -g eslint-config-standard eslint-plugin-standard eslint-plugin-promise eslint-plugin-import eslint-plugin-node
        ```
    2. 添加配置
        ```
        {
          "extends": "standard"
        }
        ```
3. html文件
    1. 安装
        ```
        npm install -g eslint-plugin-html
        ```
    2. 添加配置
        ```
        {
            "plugins": [
                "html"
            ]
        }
        ```