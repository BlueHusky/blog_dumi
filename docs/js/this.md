---
nav:
  title: this
group:
  title: this
---

## 如何确定 this 的值

```
1.Let ref be the result of evaluating MemberExpression
```

```
1.计算 MemberExpression 的结果赋值给 ref
```

```
2.If Type(ref) is Reference, then
  a.If IsPropertyReference(ref) is true, then
    i.Let thisValue be GetBase(ref).
  b.Else, the base of ref is an Environment Record
    i.Let thisValue be the result of calling the ImplicitThisValue concrete method of GetBase(ref).
  c.Else, Type(ref) is not Reference
    Let thisValue be undefined.
```

```
2.判断 ref 是不是一个 Reference 类型:
  a.如果 ref 是 Reference，并且 IsPropertyReference(ref) 是 true, 那么 this 的值为 GetBase(ref).
  b.如果 ref 是 Reference，并且 base value 值是 Environment Record, 那么this的值为 ImplicitThisValue(ref).
  c.如果 ref 不是 Reference，那么 this 的值为 undefined
```
