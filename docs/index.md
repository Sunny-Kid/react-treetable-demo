## 开始使用

基于 antd Table 组件封装的树形控件

主要提供的能力：

1. 懒加载子节点
2. 空提示子节点
3. 分页子节点
4. 筛选子节点

<code src="./Start" />

## 可受控的 expandedRowKeys

`expandedRowKeys` 和 `setExpandedRowKeys` 是 Tree 组件原生的属性。

如果从外部传入给 `TreeTable` 的话，可以使节点的展开缩起受控。

在处理复杂场景的时候比较有用，比如搜索值改变，需要重新请求数据，这个时候外部最好手动 `setExpandedRowKeys([])` 把展开节点重置为空。

## 自动展开全部节点

考虑到数据的一致性问题，TreeTable 内部不提供自动展开全部节点的功能，而是对外暴露 `resolveAllExpandableKeys` 函数，用户可以通过传入展开节点数组来实现这个功能。

### 函数签名：

```ts
export const resolveAllExpandableKeys = (
  dataSource,
  { childrenColumnName = 'children', rowKey = 'id' },
) => {};
```
