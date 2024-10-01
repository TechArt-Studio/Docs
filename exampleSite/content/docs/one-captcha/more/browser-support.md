---
linkTitle: "Browser Support"
title: Browser Support
next: docs/one-captcha/more/supported-language
prev: docs/one-captcha/more/attribute
---

All modern browsers are supported on mobile and desktop, all versions are at least 8 years old. This includes Safari, Edge, Chrome, Firefox, and Opera. Internet Explorer 11 may also work, but there are some side notes (see the section below).

## Old browser speed

{{< callout type="warning" >}}
Javascript engines in older browsers are often slower than modern browsers, and on very old browsers (>5 years) it may take up to a minute to load the CAPTCHA image and logic.
{{< /callout >}}

## NoScript

{{< callout type="warning" >}}
Users need to enable Javascript to defeat the CAPTCHA. We recommend adding a note for users who have Javascript disabled by default:
{{< /callout >}}

```html
<noscript>Please enable JavaScript to use our features</noscript>
```
