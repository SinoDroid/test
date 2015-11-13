# 注册

##### 接口说明
企业服务平台客户端申请注册用户

#####请求说明
``` http
POST /api/{版本号}/org/registration

{
	"mobile": "13312345678",
	"password": "88888888",
	"registerName": "张三",
	"email": "test@demo.com",
	"companyName": "武汉蓝筹科技有限公司",
	"mainIndustry": "IT行业",	
	"industry": "计算机软件",
	"province": "420000",
	"city": "420100",	
	"district": "420111",
	"address": "湖北省武汉市中国光谷创业产业基地一号楼14层",
	"gender": "男",	
	"title": "总经理",	
	"identityNr": "42000000000000000",
	"education": "硕士",
	"captcha": "1234",
	"sessionId": "12345678",
    "registeredCapital": "1000万",
    "turnover": "100万",						
}
```

#####参数说明
| 参数                | 是否必须        | 说明        |
|:------------------  |:--------------|:----------- |
| mobile              | 是            |手机号码      |
| password            | 是            |登录密码      |
| registerName        | 是            |注册人姓名     |
| email               | 是            |邮箱          |
| companyName         | 是            |企业名称      |
| mainIndustry        | 是            |一级行业      |
| industry            | 是            |二级行业      | 
| province            | 是            |所在省        |
| city                | 是            |所在市        |
| district            | 否            |所在区        |
| address             | 是            |企业地址      | 
| gender              | 是            |性别          | 
| title               | 是            |职位          |
| identityNr          | 是            |身份证号       |
| education           | 是            |学历           | 
| captcha             | 是            |验证码         |
| sessionId             | 是          |会话Id,由[captcha](/register/captcha.md)接口获取|
| registeredCapital   |是             |注册资金      |
| turnover            |是             |年营业额       |


#####返回说明
正确的返回:
``` json
{
    "errcode": 0,
    "message": "您的会员申请信息已成功提交,我们会评估您资料,相关审核结果会以短信方式通知到手机xxxxxxxxxx,感谢您的支持。"
}
```


错误的返回样例:
``` json
{
    "errcode": 50002,
    "message": "该手机号已被注册"
}
```
######错误代码说明
| 参数                | 说明                 | 
|:------------------ |:-------------------- |
| 500001            | 验证码错误或已过期        |
| 500002            | 该手机号已被注册        |
| 500003            | 该企业名已被注册        |
| 500004            | 用户创建失败            |

异常返回:
``` http
Response Headers:
HTTP/1.1 400 Bad Request
Content-Type: text/plain; charset=utf-8
Content-Length: 11
Date: Fri, 11 Sep 2015 03:19:38 GMT
Connection: keep-alive
```
殷玮 11/13/2015 16:24:43
* [管理平台前端API接口](admin/admin.md)
	* [通用数据](admin/common.md)
		* [行业分类](admin/common/industry.md)
		* [省份数据](admin/common/province.md)
		* [城市数据](admin/common/city.md)
		* [地区数据](admin/common/district.md)					
	* [授权](admin/auth.md)
	* [企业列表](admin/orgList.md)
	* [企业详情](admin/orgInfo.md)	
	* [新增企业](admin/orgAdd.md)	
	* [更新企业](admin/orgUpdate.md)
		* [基本信息](admin/orgUpdate/basicInfo.md)
		* [联系人信息](admin/orgUpdate/registerProfile.md)	
		* [认证信息](admin/orgUpdate/certificationInfo.md)	
		* [企业状态](admin/orgUpdate/status.md)
	* [部门列表](admin/department.md)	
	* [部门员工](admin/employeeInDept.md)	
	* [创建部门](admin/createDepartment.md)
	* [更新部门](admin/updateDepartment.md)
	* [删除部门](admin/deleteDepartment.md)												
* [管理平台第三方API接口](api/api.md)
	* [通用数据](api/common.md)
	* [注册](api/register.md)
		* [验证码](api/register/captcha.md)
		* [数据有效性验证](api/register/verify.md)
	* [信息查询](api/query.md)		
		* [用户级别](api/user/level.md)	
		* [用户所在企业](api/user/org.md)
		* [企业组织架构](api/org/structure.md)
		* [行业推荐企业](api/org/recommendation.md)
		* [企业联系人](api/org/contacter.md)	
		* [企业查询](api/org/information.md)	
