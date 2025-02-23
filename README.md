From the work of https://dagammla.gitlab.io/keep-silk-open


# Keep Silk Open!
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Z8Z7AO1BI)
## What is this?

On Amazon Echo Show devices, there currently is only one browser available. The Silk browser.

This browser will always close after some time of inactivity because of how these Amazon Echo Show devices work. This script fights this inactive state so that the browser will stay open.

---
## How?

After the user has interacted with the page at least once (e.g. touch any point on the screen),
this script will play a completely silent audio file in the background of your website and will reload it every minute. This way the silk browser will think that it is actively used.

To use this script, your web page must embed this script tag somewhere in the document:
```html
<script defer src="https://dagammla.gitlab.io/keep-silk-open/keep.js">
</script>
```

This script will only execute on browsers with `Silk` in their User Agent. To execute the script on every browser, do the following:

```html
<script>
    var AlwaysUseSilk = true
</script>
<script defer src="https://dagammla.gitlab.io/keep-silk-open/keep.js">
</script>
```

### Home Assistant Dashboard

Some people like to use this script to display their [Home Assistant](https://www.home-assistant.io/) dashboard on their Echo Show device. For this you can embed this script into your dashboard via
the Webpage/iframe card. Just add a new Webpage card to your dashboard with the following url:

```
https://dagammla.gitlab.io/keep-silk-open/iframe.html
```
---
## Test

Personally I could only test this on my Amazon Echo Show 5 2. Gen, but to test whether this will work on your Echo Show, visit this webpage:

https://dagammla.gitlab.io/keep-silk-open/test.html

Usually your browser will timeout after ~10 minutes

For debugging, it can be helpful to visualize the audio element.
To do this, write the following:
```html
<script>
    var AlwaysUseSilk = true
    var SilkVisualMode = true
</script>
<script defer src="https://dagammla.gitlab.io/keep-silk-open/keep.js">
</script>
```

---

## Experimental!
Sometimes you might want to stay on a web page that is not developed by yourself. For this you need to add a bookmark with the following url:
```
javascript:(()=>{document.body.appendChild(document.createElement("script")).src='https://dagammla.gitlab.io/keep-silk-open/keep.js';})();
```

This is only experimental as most web pages will follow a strict Content Security Policy which will prohibit this script from executing.

---

## Support

Please support me on [Ko-fi](https://ko-fi.com/Z8Z7AO1BI)
