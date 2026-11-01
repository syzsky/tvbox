# TVBox 自有源备份

- `config.json` — 站点配置，spider 指向 `https://syzsky.serv00.net/tv/jar.php;md5;c3bb107baf51fc8f90daf950c539727f`
- `spider.jar` — 959300 字节，md5 `c3bb107baf51fc8f90daf950c539727f`

## 用法

TVBox 填：`https://syzsky.serv00.net/tv/`

## 故障转移

`/tv/jar.php` 依次探测并 302 到第一个可用镜像：
1. serv00 本站
2. GitHub raw（本仓库）
3. jsDelivr
4. Cloudflare Worker
5. 原站 moji CDN

## 恢复

serv00 挂了：把本仓库的 `config.json` 和 `spider.jar` 丢到任意静态托管，改一下配置里的 spider 域名即可。
