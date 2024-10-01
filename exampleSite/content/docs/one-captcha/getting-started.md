---
linkTitle: "Getting Started"
title: Getting Started 
next: docs/one-captcha/more/attribute
weight: 1
---

This page describes how to display and customize the One Captcha v3 Developer Beta widget on your web page.

## Show One Captcha Widget

{{% steps %}}

### Step 1

Import the following One Captcha API JavaScript code into the <head> tag of your HTML page code:

```html
<script src="https://onecaptcha.us.kg/assets/v3-db/api.js"></script>
```

{{< callout type="info" >}}
  We also have a test API (this test API can use some new features, but may not be stable):
{{< /callout >}}

```html
<script src="https://onecaptcha.us.kg/assets/api/v3-db/api2.js"></script>
```

### Step 2

Add the HTML code that renders One Captcha in the <body> tag of your HTML page file:

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

After successful verification, One Captcha assigns the same ID to the data-callback function and the cookie: a one-time token. You can use this token to retrieve the result of the user's requested verification from the service. The token is valid for 15 seconds. After this time expires, it becomes invalid and the user must complete the verification process again.

### data-callback example:

```javascript {linenos=table,linenostart=1,hl_lines=[14,16]}
function CaptchaSuccess(token) {
    // Function to get the value of a cookie by name
    function getTokenCookie(name) {
        const value = `; ${document.cookie}`;
        const parts = value.split(`; ${name}=`);
        if (parts.length === 2) return parts.pop().split(';').shift();
    }

    // Get the 'OneCaptchaToken' cookie
    const cookieToken = getTokenCookie('OneCaptchaToken');

    // Compare the provided token with the cookieToken
    if (token === cookieToken) {
        // Execute your verification code here
    } else {
        // Execute the code after verification fails here
    }
}
```
