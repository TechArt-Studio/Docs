---
linkTitle: "Getting Started"
title: Getting Started 
next: docs/one-captcha/more/attribute
prev: docs/one-captcha
weight: 1
---

This page describes how to display and customize the One Captcha v3 Developer Beta widget on your web page.

## Show One Captcha Widget

{{% steps %}}

### Step 1

Import the following One Captcha API JavaScript code into the `<head>` tag of your HTML page code:

```html
<script src="https://onecaptcha.us.kg/0/api.js"></script>
```

**or** （Obfuscated version）

```html
<script src="https://onecaptcha.us.kg/0/api_lite.js"></script>
```

{{< callout type="info" >}}
  We also have a preview API (this test API can use some new features, but may not be stable):
{{< /callout >}}

```html
<script src="https://onecaptcha.us.kg/0/api_preview.js"></script>
```

### Step 2

Add the HTML code that renders One Captcha in the `<body>` tag of your HTML page file:

```html
<div id="one-captcha" data-callback="Your Callback Function"></div>
```

{{% /steps %}}

## Configuration properties

| Name | Description |
| ---- | ----------- |
| data-callback | The name of the callback function that is executed when the user submits a successful response. The one captcha token will be passed to your callback. |
| data-lang | Optional, this is a custom language, currently supported languages |

## Verify Captcha Response

After successful verification, One Captcha assigns a hashed ID to the website cookie: a one-time token. It also assigns a non-hashed token to the callback function, which you can retrieve from the cookie after encrypting the non-hashed token to a hashed value. The cookie token is valid for 15 seconds. After this time expires, the token will become invalid and the user must complete the verification process again.

### data-callback example:

```javascript {linenos=table,linenostart=1,hl_lines=[25,27]}
async function CaptchaSuccess(token) {
    // Function to retrieve the value of a cookie by name
    function getTokenCookie(name) {
        const value = `; ${document.cookie}`;
        const parts = value.split(`; ${name}=`);
        if (parts.length === 2) return parts.pop().split(';').shift();
    }

    // Get the OneCaptchaToken cookie
    const cookieToken = getTokenCookie('OneCaptchaToken');

    // Function to hash the token using SHA-512
    async function hashToken(token) {
        const encoder = new TextEncoder();
        const dataBuffer = encoder.encode(token);
        const hashBuffer = await crypto.subtle.digest('SHA-512', dataBuffer);
        const hashArray = Array.from(new Uint8Array(hashBuffer));
        const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join('');
        return hashHex;
    }

    // Compare the hashed token with the cookieToken
    const hashedToken = await hashToken(token); // Hash the passed token
    if (hashedToken === cookieToken) {
        // After successful verification, execute your code here.
    } else {
        // Execute your code here after verification fails.
    }
}

```
