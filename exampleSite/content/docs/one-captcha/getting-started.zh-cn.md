---
linkTitle: "快速开始"
title: 快速开始
next: docs/one-captcha/more/attribute
prev: docs/one-captcha
weight: 1
---

本页面描述了如何在您的网页上显示并自定义 One Captcha v3 开发者测试版小部件。

## 显示 One Captcha 小部件

{{% steps %}}

### 第一步

将以下 One Captcha API JavaScript 代码导入到您的 HTML 页面代码的 `<head>` 标签中：

```html
<script src="https://captcha.xyehr.cn/0/api.js"></script>
```

**或者** (混淆版本)

```html
<script src="https://captcha.xyehr.cn/0/api_lite.js"></script>
```

{{< callout type="info" >}}
  我们还提供了一个预览版 API（此测试 API 可以使用一些新功能，但可能不稳定）：
{{< /callout >}}

```html
<script src="https://captcha.xyehr.cn/0/api_preview.js"></script>
```

### 第二步

在您的 HTML 页面文件的 `<body>` 标签中添加渲染 One Captcha 的 HTML 代码：

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

验证成功后，One Captcha 会为网站 cookie 分配一个哈希 ID：一次性令牌。它还会为回调函数分配一个非哈希令牌，您可以在将非哈希令牌加密为哈希值后从 cookie 中检索该令牌。Cookie 令牌的有效期为 15 秒。此时间到期后，令牌将失效，用户必须重新完成验证过程。

### data-callback 示例：

```javascript {linenos=table,linenostart=1,hl_lines=[25,27]}
async function CaptchaSuccess(token) {
    // 获取指定名称的 cookie 值的函数
    function getTokenCookie(name) {
        const value = `; ${document.cookie}`;
        const parts = value.split(`; ${name}=`);
        if (parts.length === 2) return parts.pop().split(';').shift();
    }

    // 获取 OneCaptchaToken 的 cookie
    const cookieToken = getTokenCookie('OneCaptchaToken');

    // 使用 SHA-512 对 token 进行哈希的函数
    async function hashToken(token) {
        const encoder = new TextEncoder();
        const dataBuffer = encoder.encode(token);
        const hashBuffer = await crypto.subtle.digest('SHA-512', dataBuffer);
        const hashArray = Array.from(new Uint8Array(hashBuffer));
        const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join('');
        return hashHex;
    }

    // 比较哈希后的 token 与 cookieToken
    const hashedToken = await hashToken(token); // 对传入的 token 进行哈希
    if (hashedToken === cookieToken) {
        // 验证成功后执行你的代码
    } else {
        // 验证失败后执行你的代码
    }
}

```
