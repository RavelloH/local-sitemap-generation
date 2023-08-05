# local-sitemap-generation
使用本地文件生成sitemap，支持workflow自动持续构建

## 效果 
如本仓库目录下的sitemap.xml所示，可见此程序能自动将本地目录中的资源写入至sitemap.xml中，并再urlList.txt中保存中间结果。

## 使用
### 手动生成
首先，你应该根据你的文件结构更改`fileList.js`中的配置文件：

```javascript
const siteDomain = 'https://yourdomain.com/'; // 你的域名
const targetPath = './';  // 要生成sitemap的文件夹根目录
const preserveFile = './urlList.txt'; // 生成中间件urlList.txt的路径
```

之后，使用npm安装依赖，并进行生成操作 
```
npm install
node fileList.js
npx sitemap < .urlList.txt > ./sitemap.xml
```

### 自动生成
你可以使用Github Actions在文件发生更新时自动生成站点地图，参考本仓库中的`.github/workflows/sitemap.yml`设置即可
