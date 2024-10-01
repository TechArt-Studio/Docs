---
linkTitle: "浏览器支持"
title: 浏览器支持
next: docs/one-captcha/more/supported-language
---

所有现代浏览器在移动设备和桌面设备上均受支持，所有版本至少在8年内更新过。包括 Safari、Edge、Chrome、Firefox 和 Opera。Internet Explorer 11 也可能适用，但有一些附注（见下文）。

## 旧浏览器的速度

{{< callout type="warning" >}}
旧浏览器中的 Javascript 引擎通常比现代浏览器更慢，在非常旧的浏览器上（>5年），加载 CAPTCHA 图片和逻辑可能需要长达一分钟。
{{< /callout >}}

## NoScript

{{< callout type="warning" >}}
用户需要启用 Javascript 才能通过 CAPTCHA。我们建议为默认禁用 Javascript 的用户添加一条提示：
{{< /callout >}}

```html
<noscript>请启用 JavaScript 以使用我们的功能</noscript>
```
