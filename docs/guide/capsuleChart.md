---
sidebarDepth: 2
---

# 胶囊柱图

<vue-page-btn />

```html
<CapsuleChart config={config} style={{width:300px;height:200px}} />
```

<click-to-copy :info="capsuleChartTag" />

## 基本示例

<div class="chart-container" id="chart-container1"></div>

<fold-box title="点击以展示/隐藏config数据">
<<< @/docs/guide/codeData/capsuleChart/demo1.js
</fold-box>

## 单位显示

<div class="chart-container" id="chart-container2"></div>

<fold-box title="点击以展示/隐藏config数据">
<<< @/docs/guide/codeData/capsuleChart/demo2.js
</fold-box>

## 更换颜色

<div class="chart-container" id="chart-container3"></div>

<fold-box title="点击以展示/隐藏config数据">
<<< @/docs/guide/codeData/capsuleChart/demo3.js
</fold-box>

## config 属性

<full-width-table>
属性|说明|类型|可选值|默认值
:--:|:--:|:--:|:--:|:--:
data|柱数据|`Array<Object>`|[data属性](/guide/capsuleChart.html#data属性)|`[]`
unit|单位|`String`|---|`''`
colors|环颜色|`Array<String>`|[1]|[2]
</full-width-table>

## config 注释

[1] 颜色支持`hex|rgb|rgba|颜色关键字`等四种类型。

[2] 默认配色为`['#37a2da', '#32c5e9', '#67e0e3', '#9fe6b8', '#ffdb5c', '#ff9f7f', '#fb7293']`。

## data 属性

<full-width-table>
属性|说明|类型|可选值|默认值
:--:|:--:|:--:|:--:|:--:
name|柱名称|`String`|---|---
value|柱对应值|`Number`|---|---
</full-width-table>

<script>
import { render } from './utils'

import capsuleChart from './codeData/capsuleChart/index.js'

export default {
  data () {
    return {
      capsuleChartTag: '<CapsuleChart config={config} style={{width:300px;height:200px}} />',

      ...capsuleChart
    }
  },
  mounted () {
    this.renderNode()
  },
  methods: {
    renderNode () {
      Array(3).fill({ width: '300px', height: '200px' }).forEach((style, i) => render({
        r: [datav.CapsuleChart, { config: this[`capsuleChart${i + 1}`], style }],
        $: `#chart-container${i + 1}`
      }))
    }
  }
}
</script>

<style lang="less">
.chart-container {
  position: relative;
  height: 300px;
  background-color: #282c34;
  overflow: hidden;
  border-radius: 6px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #7ec699;
  font-weight: bold;
}
</style>
