## 自动导入

```jsx | pure
const lang = (req =>
  req
    .keys()
    .map(path => req(path))
    .reduce((last, current) => ({ ...last, ...current.default }), {}))(
  // 导入当前目录下 非index.js的所有js文件，require.context返回值就是上面的req
  require.context('./zh-CN', false, /^.\/(?!index)\S+.js$/),
);

export default {
  ...lang,
};
```
