#### 链克商城服务文档



本项目展示了基于链克商城合约的第三方后台服务开发示例，采用Golang语言编写，目前只提供了订单、商品相关接口代码编写，仅供开发者参考使用。



##### 使用说明

1. 首先部署链克商城合约LinkMall， 获得合约地址

2. 填写后台服务配置文件 conf/server.conf， 具体配置说明参见config.go文件

3. 编译运行程序

   ```
   cd bin
   sh make.sh
   nohup   ./linkmall_server &
   ```

   

##### 平台交互

交互流程详见 [合约与迅雷链平台交互](https://open.onethingcloud.com/site/docopen.html#6)



##### 接口说明

接口名：打包提交订单交易数据

url：/order/prepare_set

方法：POST

说明：在第三方应用中提交支付订单时调用该接口，后台服务返回已打包的交易数据，第三方应用唤起链克钱包APP发送交易，区块链后台收到交易请求，执行合约调用。



接口名：查看订单

url：/order/query

方法：POST

说明：第三方应用查询订单信息时调用该接口直接获取订单数据。



接口名：打包设置商品交易数据

url：/product/prepare_set

方法：POST

说明：在第三方应用中设置商品时调用该接口，后台服务返回已打包的交易数据，第三方应用唤起链克钱包APP发送交易，区块链后台收到交易请求，执行合约调用。



接口名：查看商品

url：/product/query

方法：POST

说明：第三方应用查询商品信息时调用该接口直接获取商品数据。















