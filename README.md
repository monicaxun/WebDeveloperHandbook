# WebDeveloperHandbook

## 20190726
- 资源加载，Status:304和Status:200（from disk cache）
  - 304：浏览器和服务器做过确认，确认了缓存的有效性，然后使用缓存
  - from disk cache：浏览器没有和服务器确认，直接使用浏览器缓存
  - 禁止from disk cache使用：请求头带上，cache:false