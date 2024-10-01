---
linkTitle: "快速开始"
title: 快速开始
next: docs/one-captcha/more/attribute
---

本页面描述了如何在您的网页上显示并自定义 One Captcha v3 开发者测试版小部件。

## 显示 One Captcha 小部件

{{% steps %}}

### Step 1

将以下 One Captcha API JavaScript 代码导入到您的 HTML 页面代码的 <head> 标签中：

```html
<script src="https://onecaptcha.us.kg/assets/v3-db/api.js"></script>
```

{{< callout type="info" >}}
  我们还提供了一个测试 API（此测试 API 可以使用一些新功能，但可能不稳定）：
{{< /callout >}}

```html
<script src="https://onecaptcha.us.kg/assets/api/v3-db/api2.js"></script>
```

### Step 2

在您的 HTML 页面文件的 <body> 标签中添加渲染 One Captcha 的 HTML 代码：

```html
<div id="one-captcha" data-callback="您的回调函数"></div>
```

{{% /steps %}}

## 配置属性

| 名称 | 描述 |
| ---- | ---- |
| data-callback | 用户提交成功响应时执行的回调函数名称，验证码 token 将传递给您的回调函数。 |
| data-lang | 可选，自定义语言，当前支持的语言列表。 |

## 验证 Captcha 响应

成功验证后，One Captcha 会将相同的 ID 分配给 data-callback 函数和 cookie：一个一次性 token。您可以使用此 token 从服务中获取用户请求验证的结果。该 token 有效期为 15 秒。此时间过后，token 失效，用户必须重新完成验证过程。

### data-callback 示例：

```javascript {linenos=table,linenostart=1,hl_lines=[14,16]}
function CaptchaSuccess(token) {
    // 获取指定名称的 cookie 值的函数
    function getTokenCookie(name) {
        const value = `; ${document.cookie}`;
        const parts = value.split(`; ${name}=`);
        if (parts.length === 2) return parts.pop().split(';').shift();
    }

    // 获取 'OneCaptchaToken' cookie
    const cookieToken = getTokenCookie('OneCaptchaToken');

    // 将提供的 token 与 cookieToken 进行比较
    if (token === cookieToken) {
        // 在这里执行您的验证代码
    } else {
        // 在验证失败后执行的代码
    }
}
```
