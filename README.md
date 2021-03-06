#### standard-validator

#### 简介：
standard-validator 用于校验javascript数据结构、分类是否正确的模块。

#### 安装方法：
通过npm进行下载安装
```$xslt
npm install standard-validator --save --save-exact
```

#### 使用方法：
standardValidator类接收两个参数，一个是校验的数据，一个是校验的规则
```$xslt
const StandardValidator = require("standard-validator");
let data = {username: "1234"};
let rules = {
    username: [
        {required: true, message: "用户名必须填写"}
    ]
};
let validator = new StandardValidator(data, rules);

// 调用validate方法进行校验，返回值true表示校验通过，返回值false，表示校验失败
validator.validate(err=>{
    // err 为null 校验通过
    // err 不为null 校验不通过
})
```

#### 现有的校验规则
| 校验规则 | 说明 |
| ---     | ---  |
| required | 必填 |
| minLength | 最小长度 |
| maxLength | 最大长度 |
| digit | 正整数 |
| min  | 最小值 |
| max  | 最大值 |
| equal | 等于指定字段的值 |
| validator | 自定义校验规则 |