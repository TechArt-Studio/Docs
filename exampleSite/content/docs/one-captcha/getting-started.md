---
linkTitle: "Getting Started"
title: Getting Started 
sidebar:
  open: true
---

This page describes how to display and customize the One Captcha v3 Developer Beta widget on your web page.

## Show One Captcha Widget

{{% steps %}}

### Step 1

Import the following One Captcha API JavaScript code into the <head> tag of your HTML page code:

```html
<script src="https://onecaptcha.us.kg/assets/v3-db/api.js"
```

{{< callout type="info" >}}
  We also have a test API (this test API can use some new features, but may not be stable):
{{< /callout >}}

```html
<script src="https://onecaptcha.us.kg/assets/api/v3-db/api2.js"
```

### Step 2

Add the HTML code that renders One Captcha in the <body> tag of your HTML page file:

```html
<div id="one-captcha" data-callback="Your Callback Function"></div>
```

{{% /steps %}}
