## 简介

本项目结合 VSCode 的 Remote - Containers 插件搭建 Node 开发环境。安装应用有 Node 和 yarn 默认安装版本如下。

| 应用 | 版本 |
| ---- | ---- |
| Node | 14.x |
| Yarn | 1.22 |

## 环境搭建

首先需要安装 Docker 如果是 windows 系统的话则是安装 docker for windows。  
其次 VSCode 需要安装 remote-containers 插件。    

### 开始使用

首先使用 VSCode 打开本项目，操作如下。  
![](.devcontainer/image/image-1.jpg)

然后选择在容器中重新打开。  
![](.devcontainer/image/image-2.jpg)

最后等待项目启动，项目启动后会将容器中的 8080 端口映射到主机的 8080 端口。  
>如要修改端口映射，可以修改 `.devcontainer\devcontainer.json` 配置文件中 `appPort` 配置项，配置值如：`<主机端口>:<容器内端口>`。  

## VSCode扩展

| 扩展名称                                 | 描述 |
| ---------------------------------------- | ---- |
| EditorConfig for VS Code                 |      |
| ESLint                                   |      |
| filesize                                 |      |
| IntelliSense for CSS class names in HTML |      |
| Live Server                              |      |
| Markdown All in One                      |      |
| Path Intellisense                        |      |
| Prettier - Code formatter                |      |
| SCSS IntelliSense                        |      |
| Todo Tree                                |      |
| TSLint                                   |      |
| Vetur                                    |      |