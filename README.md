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


## 店家界面（精简版）

首页仅展示今日订单数、今日营业额和接单列表，已删除客流曲线、热销排行、示例趋势和其他状态卡片。每日汇总按北京时间今日下单且已确认收款的 paid/ready/completed 订单统计，未付款、取消、超时和待协商订单不计入；金额以分计算，独立汇总当天全部订单，不受接单列表100条显示限制。

右下角人像“设置”按钮进入独立设置页：直接编辑店名和手机号，查看 License 状态和到期时间、验证并激活授权，查看心跳状态与最近上报时间，并可立即验证心跳。设置页保留商品管理及分类/店铺展示入口，可以返回接单。店名与电话保存到本店，顾客端自动同步；后台刷新不会覆盖未保存的输入。

工作台每20秒上报一次，超过70秒无上报显示离线；心跳只代表工作台，不代表打印机。公开 GitHub Pages 的订单、License和心跳为当前浏览器的模拟数据，不是真实商用服务端；没有跨设备共享订单。

8项每日汇总、44项静态模拟和36项本地接口检查通过，另验证手机号/店名设置、无效授权拒绝、手动心跳和手机界面导航。浏览器手机宽度检查不代表覆盖所有真机。
