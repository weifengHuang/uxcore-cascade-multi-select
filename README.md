## uxcore-cascade-multi-select

React cascade multi select

[![NPM version][npm-image]][npm-url]
[![build status][travis-image]][travis-url]
[![Test Coverage][coveralls-image]][coveralls-url]
[![Dependency Status][dep-image]][dep-url]
[![devDependency Status][devdep-image]][devdep-url]
[![NPM downloads][downloads-image]][npm-url]

[![Sauce Test Status][sauce-image]][sauce-url]

[npm-image]: http://img.shields.io/npm/v/uxcore-cascade-multi-select.svg?style=flat-square
[npm-url]: http://npmjs.org/package/uxcore-cascade-multi-select
[travis-image]: https://img.shields.io/travis/uxcore/uxcore-cascade-multi-select.svg?style=flat-square
[travis-url]: https://travis-ci.org/uxcore/uxcore-cascade-multi-select
[coveralls-image]: https://img.shields.io/coveralls/uxcore/uxcore-cascade-multi-select.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/uxcore/uxcore-cascade-multi-select?branch=master
[dep-image]: http://img.shields.io/david/uxcore/uxcore-cascade-multi-select.svg?style=flat-square
[dep-url]: https://david-dm.org/uxcore/uxcore-cascade-multi-select
[devdep-image]: http://img.shields.io/david/dev/uxcore/uxcore-cascade-multi-select.svg?style=flat-square
[devdep-url]: https://david-dm.org/uxcore/uxcore-cascade-multi-select#info=devDependencies
[downloads-image]: https://img.shields.io/npm/dm/uxcore-cascade-multi-select.svg
[sauce-image]: https://saucelabs.com/browser-matrix/uxcore-cascade-multi-select.svg
[sauce-url]: https://saucelabs.com/u/uxcore-cascade-multi-select


### Development

```sh
git clone https://github.com/uxcore/uxcore-cascade-multi-select
cd uxcore-cascade-multi-select
npm install
npm run server
```

if you'd like to save your install time，you can use uxcore-tools globally.

```sh
npm install uxcore-tools -g
git clone https://github.com/uxcore/uxcore-cascade-multi-select
cd uxcore-cascade-multi-select
npm install
npm run dep
npm run start
```

### Test Case

```sh
npm run test
```

### Coverage

```sh
npm run coverage
```

## Demo

http://uxcore.github.io/components/cascade-multi-select

## Contribute

Yes please! See the [CONTRIBUTING](https://github.com/uxcore/uxcore/blob/master/CONTRIBUTING.md) for details.

## API

## Props

| 选项 | 描述 | 类型 | 必填 | 默认值 |
|---|---|---|---|---|---|
| prefixCls | 默认的类名前缀 | String | `false`| "kuma-cascade-multi" |
| className | 自定义类名 | String | `false` | "" |
| config | 配置项 | Array | `false` | [] |
| options | 横向级联的数据 | Array | `true` | [] |
| value | 可由外部控制的值 | Array | `false` | [] |
| defaultValue | 初始默认的值 | Array | `false` | [] |
| cascadeSize | 级联层级数 | number | `false` | 3 |
| placeholder | input占位符 | string | `false` | 'Please Select' 或 '请选择' |
| noDataContent | 没有子项级联数据时显示内容 | String | `false` | 'No Data' 或 '没有数据' |
| allowClear | 是否允许清空 | bool | `false` | true |
| readOnly | 只读模式，可以查看所有选项，不可修改选中或清空 | bool | `false` | false |
| disabled | 禁用模式，只能看到结果，不可展开面板 | bool | `false` | false |
| locale | 'zh-cn' or 'en-us' | String | `false` | 'zh-cn' |
| resultPanelWidth | 结果面板的宽度 | number | `false` | 220 |
| onSelect | 选中选项的回调函数 | function | `false` | (resa, resb) => {} |

### Props.config

** 示例 **
```javascript
// 三级横向级联多选
const config = [{
  // 可以为空
}, {
  // 设置第二级不可选
  checkable: false,
}, {
  // 指定第三级宽度 220px
  width: 200,
}]
```
> 不传 config 时，默认每列宽 150px , checkable: true

> 每一列的 config 可以只配置需要的 key, 不需要全部指定， 如上示例

** 完整 config **
```javascript
// 三级横向级联多选
const config = [{
  width: 150,
  checkable: true,
}, {
  width: 150,
  checkable: true,
}, {
  width: 150,
  checkable: true,
}]
```

### Props.options

** 示例 **
```javascript
const options = [{
  value: 'zhejiang',
  label: '浙江',
  children: [{
    value: 'hangzhou',
    label: '杭州',
    children: [{
      value: 'xihu',
      label: '西湖',
    }],
  }],
}, {
  value: 'jiangsu',
  label: '江苏',
  children: [{
    value: 'nanjing',
    label: '南京',
    children: [{
      value: 'zhonghuamen',
      label: '中华门',
    }],
  }],
}];
```

### onSelect

```javascript
(resa, resb) => {
  resa: 选中选项的key列表
  resb: 选中选项的label列表
}
```
> 注：如果选项的子集全部选中，则返回该选项值
