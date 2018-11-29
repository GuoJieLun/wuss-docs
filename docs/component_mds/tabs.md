# Tabs 导航切换栏

### 使用指南

在 page.json 中引入组件

```json
"usingComponents": {
  "w-tabs": "path/to/w-tabs/index",
}
```

### 代码演示

```html
<w-pane title="Tabs" desc="导航切换栏" />

<w-pane desc="Default" />
<w-tabs bind:onChange="handleChange">
	<w-tab
	 wx:for="{{ tabs4 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>
<w-pane desc="Initial Index = 2" />
<w-button type="info" bind:click="handleSelected">selected tab2</w-button>
<w-tabs bind:onChange="handleChange" currentIndex="{{ index }}">
	<w-tab
	 wx:for="{{ tabs4 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>
<w-pane desc="Line Size = 1" />
<w-tabs lineSize="1">
	<w-tab
	 wx:for="{{ tabs1 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>
<w-pane desc="Active Color" />
<w-tabs lineSize="1" activeColor="#ff8800">
	<w-tab
	 wx:for="{{ tabs3 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>
<w-pane desc="Icon" />
<w-tabs textStyles="font-size: 14px;" activeColor="#ef473a">
	<w-tab
	 wx:for="{{ tabs2 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	 icon="{{item.icon}}"
	 iconSize="{{item.iconSize}}"
	 iconColor="{{item.iconColor}}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>
<w-pane desc="Disabled Transition and DisabledItem" />
<w-tabs transition="{{ false }}" bind:disabled="onDisabled">
	<w-tab
	 wx:for="{{ tabs4 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	 disabled="{{ index == 2 }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>

<w-pane desc="Scroll" />
<w-tabs bind:click="handleClick">
	<w-tab
	 wx:for="123456"
	 wx:key="{{index}}"
	 title="{{ 'tab' + item }}"
	>
		<view class="content">{{ item }}内容页</view>
	</w-tab>
</w-tabs>

<w-pane desc="Disabled Line" />
<w-tabs transition="{{ false }}" line="{{ false }}">
	<w-tab
	 wx:for="{{ tabs4 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>

<w-pane desc="Disabled Border" />
<w-tabs
transition="{{ false }}"
line="{{ false }}"
border="{{ false }}"
>
	<w-tab
	 wx:for="{{ tabs4 }}"
	 wx:key="{{ index }}"
	 title="{{ item.text }}"
	>
		<view class="content">{{ item.text }}内容页</view>
	</w-tab>
</w-tabs>
```

### API

#### 属性

| 属性          |          说明          |  类型   |            默认值 |
| ------------- | :--------------------: | :-----: | ----------------: |
| currentIndex  |   初始化或者控制索引   | number  |                 0 |
| transition    |    是否开启过渡动画    | boolean |              true |
| line          |      是否开启线条      | boolean |              true |
| lineSize      |    线条长度大小 0-1    | number  |               0.5 |
| border        |        开启线条        | boolean |              true |
| borderColor   |        线条颜色        | string  |              #eee |
| borderSize    |    线条粗细单位 px     | string  |                 2 |
| duration      |   设置动画时长单位 s   | number  |               0.2 |
| activeColor   |        高亮颜色        | string  | rgb(69, 143, 246) |
| textStyles    |        文本样式        | string  |                 - |
| fixed         |      是否开启定位      | boolean |             false |
| itemThreshold | 一次最多显示多少个 tab | number  |                 4 |

#### 事件

| 事件名   | 说明               | 参数         |
| -------- | ------------------ | ------------ |
| onChange | tab 变化的时候触发 | 下标 和 标题 | 
| onChange | tab 变化的时候触发 | 下标 和 标题 |

#### slot

| 名称 | 说明            |
| ---- | --------------- |
| -    | 放置 w-tab 组件 |

#### 自定义类名

| 类名       | 说明         |
| ---------- | ------------ |
| wuss-class | 根节点样式类 |
