# 建立

1. 安装 node.js(Install node.js.)
2. `npm install` 在项目目录中设置依赖关系。

# 可用命令

 - `npm run start` - 构建应用程序并运行一个Web服务器(默认情况下 [http://localhost:4400](http://localhost:4400))
 - `npm run watch` -构建应用程序和自动重建未来的变化

# 配置

 - `PORT` - 默认值 `4400`.
 - `NODE_ENV` - 可选设置此 `development` 将允许记录到控制台代替Logentries。
 - `LOGENTRIES_ACCESS_TOKEN` - 可选Logentries令牌登录请求。
 - `LOGENTRIES_APP_TOKEN` -可选Logentries令牌记录一切。
 - `ALGOLIA_API_KEY` - 可选Algolia令牌和写权限`jsDelivr` and `jsDelivr_assets` indices.

# How it works

## Project structure

 - `src/js` - server-side JavaScript. Stuff under `/api/` is a private API used by our front-end.
 - `src/public` - all client-side content - JavaScript, CSS (LESS), and images. To be bundled in the app, JS and LESS files need to be imported in `app.js`/`app.less`. 
 - `src/views` - all pages, organized as [Ractive components](http://docs.ractivejs.org/latest/components). `app.html` is the base templates for all pages, and other components are injected into `#page`.

## Search

Search is powered by [Algolia](https://www.algolia.com/). There's a [script](https://github.com/jsdelivr/www.jsdelivr.com/commit/8742343dc49b10201f4c5d864da221607d480a83#diff-902324592c72fe4414b0ff192977e0e3), which is run once a minute. It retrieves a list of all projects from our API, compares that with an in-memory copy of the index, and updates the Algolia index when necessary (only if valid `ALGOLIA_API_KEY` is set).

Some projects have too many files. In that case, a separate index (jsDelivr_assets) is used to store a list of files for each version of the project, and `assets` in the main index is set to an empty array.

In addition to project name (which has the highest priority), it also searches in author's name and project's description, and tolerates typos (1 or 2 characters).

# Auto-deploy [![Build Status](https://travis-ci.org/jsdelivr/www.jsdelivr.com.svg?branch=master)](https://travis-ci.org/jsdelivr/www.jsdelivr.com)
When code is pushed to master it is autodeployed to http://beta-jsdelivr-com.herokuapp.com.




Personal nothing to do with the original design features

1 can associate member, the member has its own list of files to use before and after the merger, for easy viewing, management
  2 corresponds to the file can be set using the Sites tab,, can also identify whether there is duplication,
  3 members can change the upload of the file (its own independent libraries, such as google can not be used in China, we need to deal with domain name).
 4  Theme and upgrade management and use of the website version Example: Website calling css and js json query cdn for a website user settings, json content can be changed directly in cdn site!
个人设计功能与原内容无关:
 1 可以关联会员,会员拥有自己使用文件列表,合并前后,方便查看,管理
 2 对应文件可以设置使用网站标签,,还可以识别是否有重复,
 3 会员可以更改上传部分文件(自己独立的库,如google在中国就不能使用,需要处理域名).
 4 管理使用网站的主题及升级版本.例:网站调用css和js为查询cdn网站用户设置的某json,json内容可直接在cdn网站更改!
 
