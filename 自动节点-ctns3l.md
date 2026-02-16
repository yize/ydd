# 自动节点

自动节点的主要用于通过配置执行动作，将第三方数据通过服务注册或 Groovy 赋值给流程中的变量。

## 第三方服务​

你可以在配置执行动作时选择已经注册成功第三方服务，然后将第三方服务的返回值，赋值给流程中的变量。
**说明**：
第三方服务需要先进行服务注册，详情请参考**服务注册**。**

##  Groovy 设置​

你可以通过 Groovy 设置对流程里的变量进行赋值，只需将流程变量名称正确填写，将所要赋的值写入执行脚本中即可。
**说明**：变量需要在流程属性中定义过。赋值字符串的时候需要加引号，例如"HelloWorld"。
赋值之后在线的执行规则中，可以用这个值去进行判断。

## 执行动作配置说明​

如果回调接口为 HTTP 接口，接口的编写要求如下：HTTP Method 为 POST。请求参数放在 RequestBody内。uuid 是系统关键字，
不能使用。如果**服务注册**的时候有使用**SHA256 签名密钥**，则需添加回调参数：__hmacSha256 md5 是服务回调默认会加的签名方式，如果**服务注册**的时候没有设置密钥，则会默认使用我们系统默认的密钥签名，如果有设置密钥，则会用设置好的密钥签名，回调参数为：sign 
你可以参考以下使用 Java 编写的简单的示例回调接口：
@RequestMapping(value = "/callback",method = RequestMethod.POST)@ResponseBodypublic List<String> callback(@RequestBody CallbackParam callbackParam) {  // 返回值格式：["工号1","工号2"]，如果返回空，直接返回null  List<String> result = new ArrayList<>();  // do something  return result;}