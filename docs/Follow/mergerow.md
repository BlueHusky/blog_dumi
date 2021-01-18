---
nav:
  title: 随笔
group:
  title: 随笔
---

## 合并行

```tsx | pure
/*
 * 多行合并方法
 * 生成合并行需要的rowSpan字段
 * datas:列表数据
 * keys：需要合并的列字段,请按列表展示排好序
 * prefix：生成合并字段的前缀
 */
export const mergeRow = (
  datas: any[],
  keys: string[],
  prefix: string,
): void => {
  // 初始化标记位
  const keyIndex: number[] = keys.map(() => 1);
  // 倒序是因为antd组件的合并行的值需要在首个赋值，例如有A、B、C行需要合并，则合并的配置值需要在A行中
  for (let i = datas.length - 1; i >= 0; i--) {
    const current = datas[i];
    const last = datas[i - 1];
    let flag = true;
    // 合并行需要满足  当前行与下一行的这一列的值相等，且当前列的前面的列的值也需要相等
    for (let j = 0; j < keys.length; j++) {
      const key = keys[j];
      if (flag && last && current[key] === last[key]) {
        current[`${prefix}${key}`] = 0;
        keyIndex[j] += 1;
      } else {
        current[`${prefix}${key}`] = keyIndex[j];
        keyIndex[j] = 1;
        flag = false;
      }
    }
  }
};
```
