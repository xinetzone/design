# 使用手册

## 1 如何从零开始搭建 Hexo 博客

1. 参考 [Hexo 安装](https://hexo.io/zh-cn/docs/)， 添加 Hexo，接着初始化项目，且命名为 `book`：

```sh
$ hexo init book
```

2. 可以替换原有的主题 `landscape`，比如选择 [matery](https://github.com/xinetzone/matery.git)：

```shell
$ git clone https://github.com/xinetzone/matery.git themes/matery
```

3. 修改配置文件 `book/_config.yml`，以匹配所需。创建 `book/_config.matery.yml` 并删除原有文件 `_config.landscape.yml`。

4. 安装一键部署工具：

```sh
$ cd book
$ npm install https://github.com/xinetzone/hexo-deployer-git.git
```

5. 生成静态网页，并部署到 GitHub Pages：

```sh
$ hexo clean && hexo g
$ hexo d
```

## 2 直接使用 `design` 作为你的博客模板

1. 进入 [xinetzone/design](https://github.com/xinetzone/design) 选择按钮 `Use this template` 即可直接使用。
2. 初始化 hexo：

```shell
$ npm i
```

3. 当然，仍需要修改 `_config.yml` 和 `_config.matery.yml`，以匹配所需。
4. 将此仓库克隆到本地，进入 `themes`，添加所需要的主题插件（你也可以替换为其他主题插件）：

```sh
$ git clone https://github.com/xinetzone/matery.git
```
5. 这样便可以开箱即用。
6. 修改 `themes/matery/layout/_partial/social-link.ejs` 可以添加新的联系方式。
7. 添加新的目录或者子目录，可以修改 `themes/matery/layout/_partial/navigation.ejs` 和 `_config.matery.yml` 的 `menu`。

## 3 Github Action 自动部署

虽然，可以通过命令 `heo clean && hexo g && hexo d` 将博文输出并部署到 Github Pages，但是，不免有点繁琐，为此，创建 `.github/workflows/pages.yml` 文件。该文件的作用是自动部署 Github Pages。故而，你只需要，使用命令 `hexo new` 创建新的博文，之后，每当你 `git push origin main`，则 Github Action 自动部署博文到 Github Pages。

具体细节见：[peaceiris/actions-gh-pages](https://github.com/peaceiris/actions-gh-pages)。