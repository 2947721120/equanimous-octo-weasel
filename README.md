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

# 怎么运行的 

## 项目结构

 - `src/js` - 服务器端JavaScript。在东西`/api/` 是由我们的前端私有API。
 - `src/public` - 所有客户端的内容 - 的JavaScript，CSS（LESS），和图像。在该应用被捆绑，JS和LESS文件需要在要导入 `app.js`/`app.less`. 
 - `src/views` - 所有页面编排 [Ractive components](http://docs.ractivejs.org/latest/components). `app.html`  `app.html`是所有页的基本模板，和其它组件被注入`#page`.

## Search

搜索是通过Algolia供电。有一个脚本，该脚本运行一次一分钟。它从我们的API的所有项目的列表，比较了与索引的内存副本，并更新Algolia指数（仅在有效ALGOLIA_API_KEY设置），必要时。 有些项目有太多的文件。在这种情况下，一个独立的索引（jsDelivr_assets）用于存储的文件的列表的每个版本的项目，并在主索引资产被设置为空数组。 除了项目名称（具有最高优先级），这也将搜索作者的姓名和项目的描述，和容忍错别字（1或2个字符）。 [Algolia](https://www.algolia.com/). There's a [script](https://github.com/jsdelivr/www.jsdelivr.com/commit/8742343dc49b10201f4c5d864da221607d480a83#diff-902324592c72fe4414b0ff192977e0e3), which is run once a minute. It retrieves a list of all projects from our API, compares that with an in-memory copy of the index, and updates the Algolia index when necessary (only if valid `ALGOLIA_API_KEY` is set).

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
 
