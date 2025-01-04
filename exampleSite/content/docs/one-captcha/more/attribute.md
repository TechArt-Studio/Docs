---
linkTitle: "Attribute"
title: Attribute
next: docs/one-captcha/more/browser-support
prev: docs/one-captcha/getting-started
weight: 1
---

| Name | Description |
| ---- | ----------- |
| data-callback | Required, The name of the callback function that is executed when the user submits a successful response. The one captcha token will be passed to your callback. |
| data-time | Required, Token validity period and Captcha expiration time (Unit: milliseconds)|
| data-lang | Optional, this is a custom language, [currently supported languages](https://docs.xyehr.cn/docs/one-captcha/more/supported-language/) |
| data-unsupport-callback | Optional, callback function for old (unsupported) browsers |
| error-callback | Optional, callback function for network interruption |
| error-recovery-callback | Optional, callback function for network connection recovery |
