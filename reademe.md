# 请把 m-only-cpt 文件夹放入项目的components文件夹内

***

## settingCell 组件 

如果该组件功能无法满足,可使用官方的 act 组件中的 cell

### 样式

![](image/setting-cell.png)

### 属性

高 48  带下边框线, 离左右各 14px 两端对齐 水平居中

### 用法

~~~html
<setting-cell title="意见反馈" :rightText="version" onclick="test()" />
~~~

### 引入

~~~js
import settingCell from '../../components/m-only-cpt/setting_cell.stml'
~~~

### 属性
  |属性                 |类型        |说明                               |是否必填         |默认值                                  |值
  :---:|:--:|:---:|:---:|:---:|:---:
  |title                |String     |左侧标题文字                        |是               |无                                    | 任意文字
  |rightText            |String     |右侧标题文字                        |否               |无                                    | 任意文字
  |hideRightArrow       |boolean    |是否隐藏右侧箭头                     |否               |false                                 | true,false
  |hideRightArrow       |boolean    |是否隐藏右侧箭头                     |否               |false                                 | true,false
  |r-text-color         |String     |右侧文字颜色                        |否               |#999                                   | 8 位颜色代码

### 备注

rightText 右侧箭头左边的文字,不填为不显示

***

## goods-cell 组件

### 样式

![](image/goods-cell.png)

### 用法

~~~html
<goods-cell :list="list" @nextList="nextList()" @openGoods="openGoods" />
~~~

### 引入
~~~js
import goodsCell from '../../components/m-only-cpt/goods-cell.stml'
~~~

### 备注
list => 传入的对象  => 包含 数据列表,列表下方待加载文字  (可针对不同的项目,进行修改组件内的字段)

                             ↑数据列表字段 

标题:name   图片:img_url   显示价格:sku_price  划线价:sku_original_price  显示包邮字段 :is_free_shipping

商品标签:goods_tag_name    服务标签:service_tag_names(数组,显示为 第一 个)


@nextList => 加载下一页的事件

@openGoods => 点击item 事件

***

## address-cell 组件

### 样式

![](image/address-cell.png)

### 用法

~~~html
<address-cell :list="list" @setDefault="setDefault" @edit="edit" @del="del" @nextList="addPage()" />
~~~

### 引入

~~~js
import AddressCell from '../../components/m-only-cpt/address-cell.stml'
~~~

### 备注


list => 传入数组 => 包含字段:

name => 收件人姓名   tel=>联系电话   map_address=> 地图定位地址  is_defaulted=> 是否为默认地址

@setDefault 设置为默认地址事件 => 只能取到 index => e.detail

@edit 点击修改按钮事件 => 只能取到 index => e.detail

@del 点击删除按钮事件 => 只能取到 index => e.detail

@nextList  加载下一页内容事件

@select  点击当前地址事件

***

## search-page 组件

### 样式

![](image/search-page.png)

### 用法

~~~html
<search-page :lists="this.data.lists" cellType_1='goods' cellType_2="cateName" cellType_3="cate"cellType_2_text="分类" :cellHeight="48" cellType_2_img="../../image/o-001.png" oncellTypeClick1="searh_goods"oncellTypeClick2="search_cate" :iconWidth="10" :iconHeight="10" />
~~~

### 引入

~~~js
import SearchPage from "../../components/m-only-cpt/search-page.stml";
~~~

### props 属性
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

###  事件
cellTypeClick1   单击预搜索关键词列表1事件

cellTypeClick2   单击预搜索关键词列表2事件

***

## home-swiper 组件

### 样式

![](image/home-swiper.png)

### props 属性
  |属性                 |类型        |说明                               |是否必填         |默认值                                  |值
  :---:|:--:|:---:|:---:|:---:|:---:
  |lists                |arr          |传入已经整理好的数组                  |是               |无                                      |[...]
  |autoplay             |boolean      |轮播图是否自动播放                    |否               |false                                   |false,true
  |mode                 |String       |图片裁剪、缩放的方式(同image标签)       |否              |scaleToFill                             |image标签内的mode
  |interval             |Number       |图片自动切换时间间隔                   |否               |5000                                    |毫秒


### 用法

~~~html
<home-swiper :lists="goodsImg" @qcSwiperIndex="getSwiperIndex" :autoplay={false} mode="scaleToFill" :interval={5000} />
~~~

### 引入

~~~js
import homeSwiper from "../../components/m-only-cpt/home-swiper.stml";
~~~

###  事件
qcSwiperIndex swiper滑动后返回的当前图片index; 可用该 index 制作 swiper 的 分页器

***

## count-botton 组件

### 样式

![](image/count-botton.png)

### props 属性
  |属性                 |类型        |说明                               |是否必填         |默认值                                  |值
  :---:|:--:|:---:|:---:|:---:|:---:
  |countTime            |Number      |传入倒计时时间                         |是               |无                                      |0~999
  |padding              |Number      |按钮距左距右距离                       |是               |默认avm button padding宽度                |任意
  |height               |Number      |按钮高度                              |是               |无                                      |20px-40px
  |borderRadius         |Number      |按钮圆角                              |否               |无                                      |1px-50px
  |fontSize             |Number      |按钮字体大小                           |否               |系统字体大小                              |5px-20px
  |isShowBorder         |boolean     |按钮是否有0.5px边框                    |否               |false                                   |true,false
  |backgroundColor      |String      |按钮背景颜色                           |否               |#FFF                                    |16进制颜色代码
  |borderColor          |String      |按钮边框颜色                          |当有边框是必填      |无                                      |16进制颜色代码
  |countText            |String      |按钮文案                              |是                |无                                     |任意   
  |color                |String      |按钮颜色                              |否               |#000                                    |16进制颜色代码
  


### 用法
~~~html
<count-botton :countTime="60" padding="14" :height="29" :borderRadius="4" :fontSize="13" :isShowBorder={true} backgroundColor="#fff" borderColor="#ff5301" countText="获取验证码" color="#ff5301" onstartCount="this.startCount" />
~~~

### 引入

~~~js
import countBotton from "../../components/m-only-cpt/count-botton.stml";
~~~

###  点击发送事件

startCount   用来让你向自己的服务器请求发送短信验证码操作

###  接收事件

qcCountStart    用来让启动倒计时

qcCountEnd      用来终止倒计时

***