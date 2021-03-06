[Demo](https://virtual-list-scroll-xfy196.vercel.app/)
### Install

```shell
npm i virtual-list-scroll
```

### Import

```shell
import Vue from "vue"
import VirtualListScroll from "virtual-list-scroll"
Vue.use(VirtualListScroll)
```

### Usage

### Page Mode

```vue
<VirtualListScroll :data="blocks">
    <template slot-scope="{data}"></template>
</VirtualListScroll>
```

### Container Mode

```vue
<VirtualListScroll :height="300" :pageMode="false" :data="blocks">
    <template slot-scope="{data}">
    </template>
</VirtualListScroll>
```

### Flxed Block Height

```vue
<VirtualListScroll
  :height="300"
  :pageMode="false"
  :flxedBlockHeight="50"
  :data="blocks"
>
    <template slot-scope="{data}">
    </template>
</VirtualListScroll>
```

### Unique virtual block

```vue
<VirtualListScroll :height="300" :pageMode="false" :data="blocks">
    <template slot-scope="{data}">
    <template v-if="data.id===0"></template>
    <template v-if="data.id===1"></template>
    </template>
</VirtualListScroll>
```
### Props
| Name             | Type          | Default | Description  |
|------------------|---------------|---------|--------------|
| data             | Array<DataObject> | -       | 必填项,列表中数组数据      |
| height           | Number        | -       | 虚拟滚动区域的高度    |
| flxedBlockHeight | Number        | -       | 每一个列表Item的高度 |
| pageMode         | Boolean       | true    | 假定滚动条是在window上还是在指定的虚拟滚动盒子上 |

### DataObjet
| Name   | Type          | Default | Description                         |
|--------|---------------|---------|-------------------------------------|
| id     | String/Number | -       | 必填项，虚拟列表渲染的唯一key                    |
| height | Number        | -       | 只有当`flxedBlockHeight`没有设定的时候才会使用这个值 |
### License
MIT