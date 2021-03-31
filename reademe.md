# settingCell 组件

#样式

![](image/setting-cell.png)

#属性

高 48  带下边框线, 离左右各 14px 两端对齐 水平居中

#用法

<setting-cell title="意见反馈" :rightText="version" onclick="test()" />

#引入

import settingCell from '../../components/setting_cell/setting_cell.stml'

#备注

rightText 右侧箭头左边的文字,不填为不显示


# goods-cell 组件

#样式

![](image/goods-cell.png)

#用法

<goods-cell :list="list" @nextList="nextList()" @openGoods="openGoods" />

#引入
import goodsCell from '../../components/cell/goods-cell.stml'

#备注
list => 传入的对象  => 包含 数据列表,列表下方待加载文字

@nextList => 加载下一页的事件

@openGoods => 点击item 事件


# address-cell 组件 (未完成,待续)

#样式

![](image/address-cell.png)

#用法

<address-cell :item="item" @setDefault="setDefault" @edit="edit" @del="del" />

#引入
import AddressCell from '../../components/cell/address-cell.stml'

#备注


item => 传入对象 => 单条记录

@setDefault 设置为默认地址

@edit 点击修改按钮

@del 点击删除按钮