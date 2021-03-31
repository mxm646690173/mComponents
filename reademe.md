# settingCell 组件 

## 如果功能无法满足,可使用官方的 act 组件中的 cell

## 样式

![](image/setting-cell.png)

## 属性

高 48  带下边框线, 离左右各 14px 两端对齐 水平居中

## 用法

`<setting-cell title="意见反馈" :rightText="version" onclick="test()" />`

## 引入

`import settingCell from '../../components/setting_cell/setting_cell.stml'`

## 备注

rightText 右侧箭头左边的文字,不填为不显示


# goods-cell 组件

## 样式

![](image/goods-cell.png)

## 用法

`<goods-cell :list="list" @nextList="nextList()" @openGoods="openGoods" />`

## 引入
`import goodsCell from '../../components/cell/goods-cell.stml'`

## 备注
list => 传入的对象  => 包含 数据列表,列表下方待加载文字

@nextList => 加载下一页的事件

@openGoods => 点击item 事件


# address-cell 组件

## 样式

![](image/address-cell.png)

## 用法

`<address-cell :item="item" @setDefault="setDefault" @edit="edit" @del="del" />`

## 引入
`import AddressCell from '../../components/cell/address-cell.stml'`

## 备注


item => 传入对象 => 单条记录

@setDefault 设置为默认地址事件 => 只能取到 index => e.detail

@edit 点击修改按钮事件 => 只能取到 index => e.detail

@del 点击删除按钮事件 => 只能取到 index => e.detail


# search-page 组件

## 样式

![](image/search-page.png)

## 用法

`<QcPreSearchPage :lists="this.data.lists" cellType_1='goods' cellType_2="cateName" cellType_3="cate"cellType_2_text="分类" :cellHeight="48" cellType_2_img="../../image/o-001.png" oncellTypeClick1="searh_goods"oncellTypeClick2="search_cate" :iconWidth="10" :iconHeight="10"></QcPreSearchPage>`

## 引入

`import SearchPage from "../../components/search-page.stml";`

## props 属性
  属性|类型|说明|是否必填|默认值|值
  :---:|:--:|:---:|:---:|:---:|:---:
  lists|arr|传入已经整理好的数组|是|无|[...]
  cellType_1|String|预搜索关键词列表1|是|无                                      
  cellType_2|String|预搜索关键词分割栏|否|无                                      
  cellType_3|String|预搜索关键词列表2|否|无                                      
  cellType_2_text|String|预搜索关键词列表分隔栏文字|否|无
  cellType_2_img|String|预搜索关键词分割栏图标|是|无|不填会导致样式有问题
  iconWidth|Number|图标宽|否|10px|支持5-20px
  iconHeight|Number|图标高|否|10px|支持5-20px
  cellHeight|Number|每一行的高度|否|48px|支持20px-70px

##  事件
cellTypeClick1   单击预搜索关键词列表1事件
cellTypeClick2   单击预搜索关键词列表2事件