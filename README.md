# 取餐有约 · 店家手机演示

[手机在线体验](https://handsomemorgan.github.io/snack-merchant-demo/)

这是单独的店家手机工作台案例，默认自动进入模拟店家，无需输入密钥。可查看预约、模拟核款出餐、维护商品及可选图片、设置联系电话和左侧分类顺序。首次打开且本店没有订单时，会添加一张明确属于模拟数据的示例订单，展示大字票据。

## 演示边界

不进行真实交易，无支付宝支付、真实打印机或营业后端。请勿输入真实个人资料。数据在访问者自己的浏览器保存；不同设备不共享。示例电话0571-0000-0000不可拨号。店家示例不是销售收入。

两个演示仓库在同一个 GitHub 域名下，在同一浏览器使用同一份模拟店铺数据：店家修改可以影响该浏览器中的顾客演示，顾客模拟预约也能出现在店家演示。不同手机或浏览器互不共享；浏览器禁用持久存储时功能可能受限。

## 打开另一个演示

[顾客点单](https://handsomemorgan.github.io/snack-customer-demo/) · [店家工作台](https://handsomemorgan.github.io/snack-merchant-demo/) · [完整多租户Demo](https://handsomemorgan.github.io/snack-pickup-demo/)

## 本地预览与更新

Node.js >=22.13：

```sh
npm ci
npm run build:pages
npm run preview:pages
```

这个仓库的构建配置已设置为 merchant 版，路径为 /snack-merchant-demo/。GitHub Pages 从 main 分支 /docs 发布。修改后重新构建并提交 docs；不要上传 .env.local、.dev.vars、数据库、实际商户密钥或报名材料。

44项浏览器模拟与30项本地接口检查已通过；已在浏览器中按320/390/430像素宽度模拟手机布局，并验证滚轮、侧栏、弹窗与点单操作；尚未覆盖所有手机真机。自动检查不证明真实支付或硬件可用。

## 来源

共享取餐有约源码。React、Vinext、Drizzle与已有shadcn组件；vendor和build中的原始许可保留。AI示意餐品图不是商家实拍。本地后端开发见LOCAL_DEVELOPMENT.md。GitHub Pages只承担功能演示，[使用限制](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits)。


## 店家今日经营看板

工作台显示今日已售订单、已核款金额、餐品份数、热销前五名，以及可切换的下单/预约取餐小时折线图。可点曲线或选择时段查看订单数和餐品份数。销售按北京时间今日下单且店家确认收款的 paid/ready/completed 订单统计；排除取消、超时和 payment_review，金额含加料，份数与排行不含单独加料。取餐曲线按今天的预约取餐时间统计，包括昨天建立、今天取餐的已核款可履约订单，表示预约量而非实测到店人数。后端独立汇总当天完整订单，不受队列100条显示限制。

公开演示可切换一整天的虚构趋势样例，明确标注，不存成订单，也不混入店家的演示订单。跨设备仍需服务端，GitHub Pages 本身没有共享订单数据库。统计专项16项、静态模拟44项、本地接口36项通过；浏览器验证手机布局，不代表已覆盖所有手机真机。
