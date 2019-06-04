# Lazy Loading Images

Lazy loading images which are not in the Viewport at the moment come native to the web. This is currently only supported in Chrome Canary and also behind a flag.

The only thing you need to do is to add the loading attribute with the value lazy to your HTML image tag.
```html
<img src="images/1.png" loading="lazy">
```

You must enable the following two flags in Chrome:
* chrome://flags/#enable-lazy-image-loading
* chrome://flags/#enable-lazy-frame-loading

If you then load this sample page you can see in Chrome Dev Tools that I load all the images. But if the server supports range requests, it only requests the first 2 KB to get the size of the image. The size is needed to display a proper placeholder. In the screenshot below you can see that there are 43 request and 134 KB transferred.

![Page Load](assets/page-load.png)

If you then scroll down to the end of the page, Chrome loads all the missing images. You can see that in the screenshot below. Now we have 61 requests and 231 KB transferred.

![Scrolled Down](assets/scrolled-down.png)
