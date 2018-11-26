# mirror-config-sankuai

[![NPM version](https://img.shields.io/npm/v/mirror-config-sankuai.svg?style=flat-square)](https://www.npmjs.com/package/mirror-config-sankuai)
[![Travis](https://img.shields.io/travis/osxfe/mirror-config-sankuai.svg?&label=Linux)](https://travis-ci.org/osxfe/mirror-config-sankuai)
[![AppVeyor](https://img.shields.io/appveyor/ci/osxfe/mirror-config-sankuai.svg?&label=Windows)](https://ci.appveyor.com/project/osxfe/mirror-config-sankuai)
[![codecov](https://img.shields.io/codecov/c/github/osxfe/mirror-config-sankuai.svg)](https://codecov.io/gh/osxfe/mirror-config-sankuai)
[![David](https://img.shields.io/david/osxfe/mirror-config-sankuai.svg)](https://david-dm.org/osxfe/mirror-config-sankuai)

为美团的 Node.js 开发者准备的镜像配置，大大提高 node 模块安装速度。

## 特性

- 支持 Windows 和其他操作系统
- 自动配置各个 node 模块的安装源为`npm.sankuai.com`镜像

## 安装

```bash
npm i -g mirror-config-sankuai --registry=http://r.npm.sankuai.com
# 查看npm配置
npm config list
# 查看环境变量
source ~/.bashrc && env
```

## 参数

### `--registry=https://registry.npm.taobao.org`

registry.npmjs.com 镜像 URL

### `--bin-mirrors-prefix=http://npm.sankuai.com/mirrors`

npm.taobao.org/mirrors 镜像 URL，会覆盖下文中的`{bin-mirrors}`

### `--apt-mirrors-prefix=https://mirrors.tuna.tsinghua.edu.cn`

mirrors.tuna.tsinghua.edu.cn 镜像 URL，会覆盖下文中的`{apt-mirrors}`

### `--ali-mirrors-prefix=https://mirrors.aliyun.com`

mirrors.aliyun.com 镜像 URL，会覆盖下文中的`{ali-mirrors}`
阿里云 ECS VPC 或经典网络用户请分别使用`http://mirrors.cloud.aliyuncs.com`或`http://mirrors.aliyuncs.com`代替

### `--nodejs-org-mirror={bin-mirrors}/node` (别名: `--disturl`)

nodejs.org/dist 镜像 URL

### `--iojs-org-mirror={bin-mirrors}/iojs`

iojs.org/dist 镜像 URL

### `--nvmw-npm-mirror={bin-mirrors}/npm`

github.com/npm/npm/releases 镜像 URL

### `--apt-mirror={ali-mirrors}`

[Debian](https://www.debian.org/mirror/list)/[Ubuntu](https://www.ubuntu.com/index_kylin) APT 镜像 URL

### `--apt-gitlab-runner={apt-mirrors}/gitlab-runner/{release-id}`

[GitLab Runner](https://docs.gitlab.com/runner/install/linux-repository.html#installing-the-runner) APT 镜像 URL

### `--apt-docker-ce={ali-mirrors}/docker-ce/linux/{release-id}`

[Docker](https://docs.docker.com/install/linux/docker-ce/debian/#install-docker-ce-1)社区版 APT 镜像 URL

### `--apt-gitlab-ce={apt-mirrors}/gitlab-ce/{release-id}`

[GitLab](https://about.gitlab.com/installation/)社区版 APT 镜像 URL

### `--apt-virtualbox={apt-mirrors}/virtualbox/apt`

[VirtualBox](https://www.virtualbox.org/) APT 镜像 URL

### `--apt-nodesource={apt-mirrors}/nodesource/deb`

[NodeJS](https://nodejs.org/zh-cn/download/package-manager/#linux-debian-ubuntu) APT 镜像 URL 前缀

### 其他

其他参数将被写入`.npmrc`文件中

## 安装成功后，针对以下组件的镜像 URL，将被写入 npm 用户配置文件(~/.npmrc)中

- [ChromeDriver](https://www.npmjs.com/package/chromedriver)
- [Electron](https://www.npmjs.com/package/electron)
- [git-win](https://www.npmjs.com/package/git-win)
- [node-gyp](https://www.npmjs.com/package/node-gyp)
- [node-inspector](https://www.npmjs.com/package/node-inspector)
- [node-sass](https://www.npmjs.com/package/node-sass)
- [node-sqlite3](https://www.npmjs.com/package/node-sqlite3)
- [nodegit](https://www.npmjs.com/package/nodegit)
- [nodist](https://github.com/marcelklehr/nodist)
- [nvm-windows](https://github.com/coreybutler/nvm-windows)
- [nvm](https://github.com/creationix/nvm)
- [OperaDriver](https://www.npmjs.com/package/operadriver)
- [phantomjs](https://www.npmjs.com/package/phantomjs)
- [Puppeteer](https://www.npmjs.com/package/puppeteer)
- [selenium-standalone](https://www.npmjs.com/package/selenium-standalone)
- [windows-build-tools](https://www.npmjs.com/package/windows-build-tools)

## 为项目生成镜像配置文件

```
cd ~/my-project
mirror-config-sankuai --registry=https://registry.npm.taobao.org
```
