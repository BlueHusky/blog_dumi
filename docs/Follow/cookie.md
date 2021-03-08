---
nav:
  title: cookie
group:
  title: cookie
---

1、Expires

- Expires 用于设置 Cookie 的过期时间。当 Expires 属性缺省时，表示是会话性 Cookie。

2、Max-Age

- Max-Age 用于设置在 Cookie 失效之前需要经过的秒数

- Max-Age 可以为正数、负数、甚至是 0。如果 max-Age 属性为正数时，浏览器会将其持久化，即写到对应的 Cookie 文件中，当 max-Age 属性为负数，则表示该 Cookie 只是一个会话性 Cookie，当 max-Age 为 0 时，则会立即删除这个 Cookie

- 假如 Expires 和 Max-Age 都存在，Max-Age 优先级更高

3、Domain

- Domain 指定了 Cookie 可以送达的主机名，不能跨域设置 Cookie

4、Path

- Path 指定了一个 URL 路径，这个路径必须出现在要请求的资源的路径中才可以发送 Cookie 首部。

- 比如设置 Path=/docs，/docs/Web/ 下的资源会带 Cookie 首部，/test 则不会携带 Cookie 首部。Domain 和 Path 标识共同定义了 Cookie 的作用域：即 Cookie 应该发送给哪些 URL。

5、Secure

- 标记为 Secure 的 Cookie 只应通过被 HTTPS 协议加密过的请求发送给服务端。

6、HTTPOnly

- 设置 HTTPOnly 属性可以防止客户端脚本通过 document.cookie 等方式访问 Cookie，有助于避免 XSS 攻击

7、SameSite

- SameSite 属性可以让 Cookie 在跨站请求时不会被发送，从而可以阻止跨站请求伪造攻击（CSRF）

```tsx | pure
1、Strict 仅允许一方请求携带 Cookie，即浏览器将只发送相同站点请求的 Cookie，即当前网页 URL 与请求目标 URL 完全一致。
2、Lax 允许部分第三方请求携带 Cookie
3、None 无论是否跨站都会发送 Cookie
之前默认是 None，Chrome80 后默认是 Lax
```

- 跨域和跨站

```tsx | pure
跨域：端口、协议、域名不一致就会产生跨域
跨站：只要两个 URL 的 eTLD+1 相同即可，不需要考虑协议和端口
www.taobao.com 和 www.baidu.com 是跨站，www.a.taobao.com 和 www.b.taobao.com 是同站，a.github.io 和 b.github.io 是跨站(注意是跨站)。
```
